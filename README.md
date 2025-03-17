# Projeto-Individual-1-Agencia-de-Viagens
Projeto da Recode Pro AI - 2024/2025

### Segue a modelagem de banco de dados conceitual:
![image](https://github.com/user-attachments/assets/cf16430d-813a-48e1-86ac-c2746df21750)

### Modelagem de dados lógica:
![Screenshot_20250316_221848](https://github.com/user-attachments/assets/0d89e324-2b0f-40dd-b14d-2050c12ee0d1)


### Script - sql:

CREATE TABLE cliente ( <p>
    cpf BIT PRIMARY KEY, <p>
    nome CHARACTER,<p>
    endereço CHAR,<p>
    telefone CHAR,<p>
    e-mail CHAR<p>
);<p>
<p>
CREATE TABLE voo_hospedagem (<p>
    data BIT,<p>
    numero CHAR,<p>
    cidade CHAR,<p>
    hotel CHAR,<p>
    PRIMARY KEY (numero, hotel)
);<p>
<p>
CREATE TABLE passaporte (<p>
    número CHAR PRIMARY KEY,<p>
    data CHARACTER,<p>
    destino CHARACTER<p>
);<p>
<p>
CREATE TABLE aquisição (<p>
    fk_passaporte_número CHAR,<p>
    fk_cliente_cpf BIT<p>
);<p>
<p>
CREATE TABLE viagem (<p>
    fk_passaporte_número CHAR,<p>
    fk_voo_hospedagem_numero CHAR<p>
);<p>
 <p>
ALTER TABLE aquisição ADD CONSTRAINT FK_aquisição_1<p>
    FOREIGN KEY (fk_passaporte_número)<p>
    REFERENCES passaporte (número)<p>
    ON DELETE RESTRICT;<p>
 <p>
ALTER TABLE aquisição ADD CONSTRAINT FK_aquisição_2<p>
    FOREIGN KEY (fk_cliente_cpf)<p>
    REFERENCES cliente (cpf)<p>
    ON DELETE RESTRICT;<p>
 <p>
ALTER TABLE viagem ADD CONSTRAINT FK_viagem_1<p>
    FOREIGN KEY (fk_passaporte_número)<p>
    REFERENCES passaporte (número)<p>
    ON DELETE RESTRICT;<p>
 <p>
ALTER TABLE viagem ADD CONSTRAINT FK_viagem_2<p>
    FOREIGN KEY (fk_voo_hospedagem_numero, ???)<p>
    REFERENCES voo_hospedagem (numero, ???)<p>
    ON DELETE RESTRICT;<p>
