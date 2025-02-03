# LH_ED_JOSERODRIGUEZ

## Descrição
Este projeto é uma solução de pipeline de dados que utiliza o Apache Airflow e o Meltano para extrair, transformar e carregar (ETL) dados de um banco de dados PostgreSQL e de arquivos CSV. O objetivo é facilitar a integração de dados de diferentes fontes e garantir que os dados estejam disponíveis para análise e relatórios.

### Principais Funcionalidades
- Extração de dados de um banco de dados PostgreSQL.
- Extração de dados de arquivos CSV.
- Carregamento de dados processados de volta em um banco de dados PostgreSQL.
- Agendamento de tarefas usando o Apache Airflow.

## Instalação

### Pré-requisitos
- Python 3.7 ou superior
- Meltano: 3.6.0
- Docker e Docker-Compose
- Apache Airflow

### Configuração Do Ambiente
1. Clone o repositório:
    git clone https://github.com/jarodri26/LH_ED_JOSERODRI.git
    cd LH_ED_JOSERODRI
   

2. Crie um ambiente virtual (opcional, mas recomendado):
   ```bash
   python -m venv venv
   source venv/bin/activate  # Para Linux/Mac
   # ou
   venv\Scripts\activate  # Para Windows
   ```

3. Implemente a arquitetura de Airflow para docker-compose.yml
    https://airflow.apache.org/docs/apache-airflow/2.10.4/docker-compose.yaml

4. usei dos bancos de dados Posgres, um de origem do banco northwind e um de destino, northwind-final

    Excutar o comando "docker-compose up -d" dentro da pasta LH_ED_JOSERODRI    

## Uso

Após a instalação e configuração, você pode acessar a interface web do Airflow em `http://localhost:8080`. A partir daí, você pode ativar e executar o DAG que foi configurado para o pipeline de dados.


### Exemplo de Comando
Para executar o pipeline manualmente, você pode usar o seguinte comando usando Meltano desde o terminal:
   ```bash
   meltano run tap-postgres target-postgres
   meltano run tap-csv target-postgres
   ```