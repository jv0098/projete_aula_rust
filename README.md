# 🎬 Theater Website

## 📋 Project Description

The "**Theater Website**" is a web application forked off by me from a group of university acquaintances, the main goal is being to adapt it to the MySQL connection application, in addition to authentication.

The application simulates an website like "Netflix" and other streamings, giving you access to some features:

- Login and Sign-Up
- Choose a Movie
- Bought your Film
- Watch the content chosen

> 💡 The model is a "*pay-per-view*" without a monthly payment.

---

## 🛠️ Technologies used

| Technology | Description |
|-----------|-----------|
| Rust (actix-web) | Backend responsable for all logic |
| MySQL | Database used for store the data |
| HTML5 | Structure for the frontend |
| CSS3 | Style for the HTML |
| JavaScript | Some dynamic between frontend and backend |

---

## 🏗️ Estrutura do Projeto

```Mathematical
FILME-TESTE/
├── src/
│ └── main.rs
| └── banco.rs
├── static/
│ ├── img/
│ ├── login.html 
│ ├── escolher.html 
│ ├── pagamento.html
│ └── assistir.html 
├── .gitignore
├── Cargo.toml
├── Cargo.lock
└── README.md
```

---

## 📄 Funcionalidades

- 🔐 **User's Login:** Authentication Between MySQL and Rust.
- 🎞️ **Choose a Movie:** Movie's List for the user.
- 💳 **Payment System (Simulation):** Buy a single movie and watch it.
- ▶️ **Content Visualization:** Page with the content in order for you to watch.

---

## 🚀 How to execute the project

### ✅ Pre-requisites:

- [Rust](https://www.rust-lang.org/tools/install)
- [MySQL](https://dev.mysql.com/downloads/mysql/) installed and configurated
- Modern Browser (Brave, Firefox, etc.)

### 🔧MySQL Configuration

Before use it, you must execute the following statement on MySQL:

```sql
DROP DATABASE IF EXISTS cine;
CREATE DATABASE IF NOT EXISTS cine;
USE cine;

CREATE TABLE IF NOT EXISTS usuarios (
    id_usuario INT PRIMARY KEY AUTO_INCREMENT,
    nome_usuario VARCHAR(100) NOT NULL,
    email_usuario VARCHAR(100) UNIQUE NOT NULL,
    senha_usuario VARCHAR(255) NOT NULL
);

CREATE TABLE IF NOT EXISTS Filmes (
    id_filme INT PRIMARY KEY AUTO_INCREMENT,
    titulo_filme VARCHAR(255) NOT NULL,
    genero_filme VARCHAR(100),
    clacifi_filme VARCHAR (100),
    data_filme DATE
);

CREATE TABLE IF NOT EXISTS Administradores (
    id_admin INT PRIMARY KEY AUTO_INCREMENT,
    nome_admin VARCHAR(100) NOT NULL,
    email_admin VARCHAR(100) UNIQUE NOT NULL,
    senha_admin VARCHAR(255) NOT NULL,
    data_cadastro_admin TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    usuario_id INT, 
    filme_id INT,
    FOREIGN KEY (usuario_id) REFERENCES Usuarios(id_usuario),
    FOREIGN KEY (filme_id) REFERENCES Filmes(id_filme)
);
```

### Try it yourself!

1. Clone it
```bash
git clone https://github.com/seu-usuario/filme-teste.git
cd filme-teste
```

2. Execute
```bash
cargo run
```

3. Access it through your browser
```
http://localhost:8080/
```


