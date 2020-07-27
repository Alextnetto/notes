#Learn_Postgres

Instale libpq-dev, pode poupar de alguns problemas inesperados:
```bash
sudo apt-get install libpq-dev
```

Acessar o user postgres:
```bash
sudo -u postgres -i
```

Acessar a database:
```bash
psql $database
```

Acessar a database com user específico:
```bash
psql $database -U $user
```

Listar (somente quando já estiver no shell da database):
```bash
\du # Users
\l  # Databases
\dt # Tables
```