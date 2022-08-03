# CRUD-MVC-POO-com-PHP

## conexão com banco de dados:
```php
<?php

    //constantes da conexão do banco de dados (nome_da_variavel, valor_da_variavel)
    define('HOST', 'localhost');  
    define('DBNAME', 'crud-mvc-php');
    define('USER', 'root');
    define('PASSWORD', 'root');

    class Connect{
        protected $connection; // variavel que pode ser acessado tanto na classe quanto para seus filhos

        function __construct(){
            $this->connectDatabase();
        }

        private function connectDatabase(){
            try 
            {
                $this->connection = new PDO('mysql:host='.HOST.';dbname='.DBNAME, USER, PASSWORD); // faz a conexão
            } 
            catch (PDOException $e) 
            {
                echo "Error to connect with Database!".$e->getMessage(); // ler menssagem de erro
                die(); // fecha chamada com o banco de dados
            }
        } 

    }
?>
```

## MVC 
MVC é antes de mais nada uma arquitetura que permite dividir o desenvolvimento da aplicação em três camadas conceituais: Model, View e Controller (Modelo - Visão - Controlador).

- *MODEL* seria a parte da modelagem de dados e regras de negócio. É nela que vão constar as classes , as consultas ao banco de dados e as regras de negócio do sistema.

- *ViEW* é a parte estética, a interface. É a "tela" onde os dados e os links serão apresentados ao usuário. De grosso modo, um arquivo somente com códigos HTML e CSS (e se tiver, o Javascript também)

- *CONTROLLER* seria a parte do controle do sistema. É ele quem faz as ligações das diversas partes do sistema, recebe e valida os dados fornecidos na entrada de dados das views, faz a ligação dos dados com as regras de negócios e as consultas a base de dados dos models, processa a requisição e retorna um resultado, geralmente em uma nova view.

### Arquivo CONTROLLER
- 
