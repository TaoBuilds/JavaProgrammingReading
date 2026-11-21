# JDBC educational project: local credential safety

The old `JDBCMessageBoard` course example previously stored a password directly
in `ConnectionUtil.java`. This is insecure, even for learning code.

To run the example locally, configure environment variables rather than editing
credentials into source:

```sh
export JDBC_URL='jdbc:mysql://localhost:3306/message_board'
export JDBC_USER='your_local_db_user'
export JDBC_PASSWORD='your_local_db_password'
```

On Windows use the appropriate PowerShell environment syntax.

The old Java source still targets the historic MySQL driver and should be treated
as an archived learning exercise, **not** production application code.

A new `.gitignore` prevents future additions of common IDE and compilation
files, but files already tracked in Git are not automatically removed.

**Important:** Removing a password in the current branch does not remove it from
Git history. If the old password was ever reused for a real database or service,
rotate it. Do not casually rewrite public repository history without coordinating
with existing clones and links.
