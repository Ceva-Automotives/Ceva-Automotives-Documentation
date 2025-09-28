# Entrega 01 - 29/09/2025

## Como rodar o backend e o banco de dados?

### Criar as tabelas no PostgresSQL

```bash
python init_db.py
```
- dar refresh na conexão

### Criar carro
- Iniciar o servidor:
```bash
python -m uvicorn app.main:app --reload
```

- No DBeaver:

```bash
INSERT INTO carros (
    marca, modelo, ano, cor, 
    "precoDia",
    descricao, disponivel, destaque,
    "criadoEm", "atualizadoEm"
 ) VALUES (
    'Zeekr', 'Zeekr 009', 2024, 'Prata',
    180.0, 
    'Carro elétrico', true, true,
    NOW(), NOW()
);
INSERT INTO carros (
    marca, modelo, ano, cor, 
    "precoDia",
    descricao, disponivel, destaque,
    "criadoEm", "atualizadoEm"
 ) VALUES (
    'Zeekr', 'Zeekr 001', 2025, 'Branco',
    300.0, 
    'Carro elétrico', true, true,
    NOW(), NOW()
);
INSERT INTO carros (
    marca, modelo, ano, cor, 
    "precoDia",
    descricao, disponivel, destaque,
    "criadoEm", "atualizadoEm"
 ) VALUES (
    'Toyota', 'Corola', 2010, 'Preto',
    180.0, 
    'Sedan', true, true,
    NOW(), NOW()
);
```
```bash
SELECT * FROM carros ORDER BY id DESC;
```

- Testar os Endpoints:
```bash
# Listar todos os carros
curl http://127.0.0.1:8000/carros/

# Buscar por ID
curl http://127.0.0.1:8000/carros/1

# Contar carros
curl http://127.0.0.1:8000/carros/count/

# Buscar por marca
curl http://127.0.0.1:8000/carros/marca/Zeekr
```

