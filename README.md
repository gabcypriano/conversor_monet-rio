# conversor_monet-rio
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>$DevConverter</title>
        <!--CSS-->
        <link rel="stylesheet" href="./css/reset.css">
        <link rel="stylesheet" href="./css/header.css">
        <link rel="stylesheet" href="./css/footer.css">
        <link rel="stylesheet" href="./css/main.css">
        <!--Fonts-->
        <link rel="preconnect" href="https://fonts.googleapis.com">
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
        <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@200;300&family=Poppins:wght@500;600;700&display=swap" rel="stylesheet">
        
    </head>
<body>
    <header>
        <h1>$DevConverter</h1>
    </header>
    <main>
        <form id="form">
            <section class="inputs-container">
                <div class="form-group">
                    <label for="value-real">Valor a ser convertido (R$)

                    </label>
                    <input type="number" placeholder="R$20,00" id="value-real" name="value-real"
                    max="1000000">
                </div>

                <div class="form-group">
                    <label for="">Escolha a moeda

                    </label>
                    <select id="currency">
                        <option value="">selecione...</option>

                        <option value="eur">Euro</option>

                        <option value="dol">Dólar</option>
                    </select>
                   
                </div>

            </section>
            <button type="submit">Converter</button>

            <h2 id="result"></h2>
        </form>
    </main>

    <footer>
        <span>
            &copy; $DevConverter,2023. Todos os direitos reservados.
        </span>
    </footer>
    <script src="script.js"></script>
</body>
</html>
