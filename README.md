# Sistema de Monitoramento Agrícola — MER

Este projeto tem como objetivo a criação de um Modelo Entidade-Relacionamento (MER) para um sistema de monitoramento agrícola.

## Entidades Modeladas

### Fazenda
- `id_fazenda` (PK)
- `nome_fazenda` VARCHAR(20)
- `loc_fazenda`  VARCHAR(100)
- `area_plantio` FLOAT(10,2)
- `unidade_medida_area` VARCHAR(20)

### Cultura
- `id_cultura` (PK)
- `id_fazenda` (FK)
- `nome_cultura` VARCHAR(20)
- `tipo_cultura` VARCHAR(20)
- `area_cultura` FLOAT(10,2)
- `data_plantio` DATETIME
- `data_colheita` DATETIME
- `status_cultura` VARCHAR(20)

### Sensor_Umidade
- `id_sensor_umidade` (PK)
- `id_cultura` (FK)
- `umidade_registrada` FLOAT(5,2)
- `var_umidade` INTEGER
- `quantidade_aplic` INTEGER
- `unidade_med_umi` VARCHAR(20)
- `data_hora_aplic` DATETIME
- `status_sensor` VARCHAR(20)
- `loc_sensor` VARCHAR(100)

### Sensor_PH
- `id_sensor_ph` (PK)
- `id_cultura` (FK)
- `ph_registrado` FLOAT(3,2)
- `valor_ph` FLOAT(3,2)
- `variacao_ph` FLOAT(3,2)
- `data_hora` DATETIME
- `status_sensor` VARCHAR(20)
- `loc_sensor` VARCHAR(100)

### Sensor_Nutrientes
- `id_sensor_nutri` (PK)
- `id_cultura` (FK)
- `var_nutri` FLOAT(5,2)
- `dt_aplic_nutri` DATETIME
- `status_sensor` VARCHAR(20)
- `loc_sensor` VARCHAR(100)

### Nutriente_Registrado
- `id_nutri` (PK)
- `id_sensor_nutri` (FK)
- `nome_nutri` VARCHAR(20)
- `quantidade_reg` FLOAT(7,2)
- `unidade_medida` VARCHAR(20)
- `dt_registro` DATETIME

## Relacionamentos

| Entidade Origem      | Entidade Destino        | Tipo |
|----------------------|-------------------------|------|
| Fazenda              | Cultura                 | 1:N  |
| Cultura              | Sensor_Umidade          | 1:N  |
| Cultura              | Sensor_PH               | 1:N  |
| Cultura              | Sensor_Nutrientes       | 1:N  |
| Sensor_Nutrientes    | Nutriente_Registrado    | 1:N  |


## Integrantes do Grupo

- Arthur Luiz Rosado Alves  -> RM562061
- Thiago Henrique Pereira de Almeida Santos -> RM 563327



