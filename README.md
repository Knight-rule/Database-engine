<h1 align="center">🗄️ In-Browser SQL Database Engine</h1>

<p align="center">
  <em>Full SQL database running entirely in your browser — parser, query engine, and B+ tree indexing</em>
</p>

<p align="center">
  <a href="https://knight-rule.github.io/database-engine"><img src="https://img.shields.io/badge/demo-live-brightgreen" alt="Live Demo"></a>
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white" alt="CSS3">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black" alt="JavaScript">
</p>

---

## ✨ Features

- [x] **SQL Parser** — Parses standard SQL syntax into an execution plan
- [x] **Full CRUD** — CREATE, INSERT, SELECT, UPDATE, DELETE operations
- [x] **JOINs** — INNER JOIN, LEFT JOIN with multi-table queries
- [x] **GROUP BY** — Aggregate queries with COUNT, SUM, AVG, MIN, MAX
- [x] **B+ Tree Indexing** — Efficient indexed lookups with visual tree
- [x] **EXPLAIN** — View query execution plans
- [x] **Storage Visualization** — Watch data pages fill up in real-time
- [x] **Demo Database** — Pre-loaded with sample data for immediate exploration
- [x] **Zero Dependencies** — Pure vanilla JavaScript

## 📸 Screenshot

![screenshot](screenshot.png)

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML5 | SQL editor and result display |
| CSS3 | Storage visualization and responsive layout |
| JavaScript | SQL parser, query engine, B+ tree implementation |

## 🚀 Installation

```bash
# Clone the repository
git clone https://github.com/knight-rule/database-engine.git

# Navigate to the project
cd database-engine

# Open in browser
open index.html
```

No build step or dependencies required — just open the HTML file!

## 📖 Usage

1. **Type SQL** — Enter queries in the editor (try the demo queries!)
2. **Execute** — Click "Run Query" or press Ctrl+Enter
3. **View Results** — Results appear in the table below
4. **Check Execution Plan** — Use EXPLAIN to see how queries are processed
5. **Watch Storage** — See data pages and B+ tree update in real-time

```sql
-- Create a table
CREATE TABLE users (id INT, name VARCHAR, email VARCHAR, age INT);

-- Insert data
INSERT INTO users VALUES (1, 'Alice', 'alice@example.com', 30);
INSERT INTO users VALUES (2, 'Bob', 'bob@example.com', 25);

-- Query with JOIN and GROUP BY
SELECT users.name, orders.total
FROM users
INNER JOIN orders ON users.id = orders.user_id
WHERE users.age > 21
GROUP BY users.name;
```

## ⚙️ How It Works

```
┌─────────────┐    ┌──────────────┐    ┌─────────────┐
│  SQL Query   │───▶│  SQL Parser  │───▶│ Query Plan  │
│  (string)    │    │  (tokens →   │    │  (tree of   │
│              │    │   AST)       │    │   operations)│
└─────────────┘    └──────────────┘    └──────┬──────┘
                                              │
                         ┌────────────────────┘
                         ▼
┌─────────────┐    ┌──────────────┐    ┌─────────────┐
│  Results    │◀───│  Executor    │◀───│  B+ Tree    │
│  (table)    │    │  (operates   │    │  Index      │
│              │    │   on data)   │    │             │
└─────────────┘    └──────────────┘    └─────────────┘
```

The engine operates like a real database:
1. **Parsing** — SQL string → tokens → Abstract Syntax Tree
2. **Planning** — AST → execution plan with optimal scan strategies
3. **Execution** — Plan nodes are evaluated bottom-up
4. **Indexing** — B+ tree provides O(log n) lookups for indexed columns
5. **Storage** — Data organized in pages with buffer management

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Prashant** — [@knight-rule](https://github.com/knight-rule)

<p align="center">
  Made with ❤️ for database enthusiasts
</p>
