### Criando usuario no postgresSQL
```sql
 CREATE USER '`USUARIO`' WITH ENCRYPTED PASSWORD '`SENHA`';
```
### Criando banco

```sql
CREATE DATABASE <banco>
```

### Garantindo privilegios

```sql
GRANT ALL PRIVILEGES ON DATABASE <banco> TO <usuario>;
```

### ALTERANDO SENHA DO USUARIO

```sql
 ALTER USER <usuario> WITH WITH ENCRYPTED PASSWORD <senha>;
```
### Criando extensão para uso o uuid 
```sql
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
```

### Criando banco de dados e selecionando ele 

```sql
CREATE DATABASE meudb;
\c meudb;
```

