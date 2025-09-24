# Smart Grouping Tool

[![License: AGPL v3](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)

A powerful, browser-based, single-page application for intelligently dividing participants into groups based on a sophisticated set of user-defined rules. Ideal for teachers, event organizers, and anyone needing to create balanced and logical groups from a list of people.

## 💡 Motivation

This tool was created to make powerful, rule-based grouping accessible to everyone, especially those without a technical background. It was inspired by the Python program `GroupEng` but is designed to overcome common usability hurdles for non-programmers.

Setting up a Python environment and running scripts can be a significant barrier. Furthermore, `GroupEng` requires data in a CSV format, which can be unfamiliar to many. This tool simplifies everything:

1.  **It's just one file:** All you need is `index.html`. No installation, no command line.
2.  **It uses Excel:** It accepts the `.xlsx` file format that most users already know and use.

While the capabilities are similar to `GroupEng`, this application is a completely new implementation with its own optimization algorithm, built from the ground up for simplicity and ease of use.

## ✨ Key Features

*   **Entirely Client-Side:** Runs completely in your browser. No server, no data uploads, ensuring 100% privacy.
*   **Excel Support:** Simply drag and drop your participant list (`.xlsx`) to get started.
*   **Flexible Grouping Modes:**
    *   Group by a fixed **size** (e.g., 4 members per group).
    *   Group by a total **number** of groups.
    *   Define **custom sizes** for each group individually (e.g., 5, 5, 4, 4).
*   **Powerful Rules Engine:** Combine multiple rules to create the perfect grouping:
    *   **Balance:** Make the average of a numeric value (like scores) even across all groups.
    *   **Distribute:** Ensure proportional representation of categories (like gender or department).
    *   **Cluster:** Avoid isolating individuals of a certain type in a group.
    *   **Aggregate:** Force specific members to be in the *same* group.
    *   **Separate:** Force specific members to be in *different* groups.
*   **Advanced Optimization:** Uses a **Simulated Annealing** algorithm to find a near-optimal solution for complex rule sets.
*   **Visual Reporting:** Results are displayed with clear statistics, summaries, and charts to visualize the distribution of members.
*   **Light & Dark Mode:** A modern interface that respects your system preferences and can be toggled manually.
*   **Export Results:** Download the final grouping as a new Excel file with one click.
*   **Zero Installation:** It's a single HTML file. Just download and open it in your browser.

## 🚀 How to Use

1.  **Download:** Download the `index.html` file from this repository.
2.  **Open:** Open the `index.html` file in any modern web browser (like Chrome, Firefox, or Edge).
3.  **Upload Data:** Drag and drop your Excel file (`.xlsx`) onto the upload zone, or click to select it. Your file must have a header row with column titles.
4.  **Configure:**
    *   Choose your desired **Grouping Mode**.
    *   Select the column that uniquely identifies each person (e.g., "Name" or "ID").
    *   Add and configure rules based on the columns in your data.
    *   Adjust the **Optimization Level**—"Standard" is great for most cases.
5.  **Generate:** Click the "Generate Groups" button.
6.  **Review & Download:** Analyze the results summary and the generated groups. If you're satisfied, click "Download Grouping Results" to get an Excel file.

## ⚙️ The Rules Engine Explained

The power of this tool lies in its flexible rules, which can be prioritized by dragging them into your desired order.

| Rule        | Purpose                                                                    | Example                                                                                              |
| :---------- | :------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------- |
| **Balance**   | (Numeric) Evens out the average of a numeric column across all groups.     | Balance "Test Score" to create academically heterogeneous groups.                                     |
| **Distribute**| (Categorical) Spreads members of different categories proportionally.      | Distribute "Gender" to ensure a similar male-to-female ratio in each group.                          |
| **Cluster**   | (Categorical) Prevents a single member of a category from being alone.     | Cluster "Club Members" to ensure a group has either zero or at least two members from the same club. |
| **Aggregate** | (Categorical - Hard Constraint) Forces members with a specific value into the same group. | Aggregate members by "Project ID" so that all students working on project `A01` are grouped together. |
| **Separate**  | (Categorical - Hard Constraint) Forces members with a specific value into different groups. | Separate members by "Role" to ensure each group has at most one "Team Leader".                       |

## 📜 License

This project is licensed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.

This means you are free to use, study, share, and modify the software. However, if you run a modified version of this software on a server and let others interact with it over a network, you must also make your modified source code available to them under the same license. See the [full license text](https://www.gnu.org/licenses/agpl-3.0.html) for details.