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

#Java Script


const form = document.getElementById('form');
form.addEventListener('submit',handleSubmit)

const inputValue = document.getElementById('value-real');
const selectedCurrency = document.getElementById('currency');
const result = document.getElementById('result');

function handleSubmit(e){
    e.preventDefault();
    if(!inputValue.value || inputValue.value < 0){
    alert('Informe o valor correto!');
    return;
    } else if(!selectedCurrency.value){
        alert('Escolha uma moeda!')
    }
    converter();
}; 

function converter(){
    if(selectedCurrency.value === 'eur') {
        valueConverted = inputValue.value * 5.60;
        result.innerHTML = valueFormatter('pt-BR','EUR');

        animateResult();
    } else if(selectedCurrency.value === 'dol') {
        valueConverted = inputValue.value * 5.29;
        result.innerHTML = valueFormatter('en-US','USD');

        animateResult();
    }

    inputValue.value = '';
    selectedCurrency.value = '';
};

function valueFormatter(Locale, currency ){
    const value = valueConverted.toLocaleString(`${Locale}`, {style: 'currency', currency: `${currency}`});
    return `<span> 🤑 </span> ${value} <span> 🤑 </span>`;
};

function animateResult(){
    return result.animate([
        {transform: 'translateY(-150px)'},
        {transform: 'translateY(0px)'},

    ], { duration: 500});

};

#CSS

footer{
    width: 100%;
    background-color: #5aba8d;
    padding:10px;
    text-align: center;
}

footer span{
    color:#fff;
    font-size: 0.8em;
    font-weight: 500;
}

header{
    width: 100%;
    background-color: #5aba8d;
    padding: 20px;

}

header h1{
    color: #fff;
    font-size: 3em;
    text-align: center;
    cursor: pointer;
}

main{
    width: 60%;

    display:flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

form{
    width: 100%;
    margin-bottom: 12%;

    display: flex;
    flex-direction: column;
    align-items: center;
}

.inputs-container{
    width: 100%;
    display: flex;
    justify-content: space-around;
    margin-bottom: 8%;
}

.form-group{
    display: flex;
    flex-direction: column;
}

.form-group label{
    color: #333;
    font-size: 0.8;
    font-weight: 600;
    margin-bottom: 6px;
}

form button {
    background-color: #5aba8d;
    color: #fff;
    font-size: 1.2em;
    font-weight: 700;
    cursor: pointer;
}

form button:hover{
    background-color: #fff;
    color: #5aba8d;
}

main #result{
    font-size: 3.5em;
    color: #2f9766;
}

main #result span{
    font-size: 0.6em;
    margin-right: 50px;
    margin-left: 50px;
}

*{
    margin: 0;
    padding:0;
    box-sizing: 0;
    font-family: 'Poppins', sans-serif;

}

body {
    background-color: #eee;
    width: 100%;
    height: 100vh;

    display:flex;
    flex-direction: column;
    align-items: center;
    justify-content:space-between;

}

input, select, button{
    border:0;
    outline: 0;
    border-radius: 6px;
    width: 220px;
    padding: 10px 14px;
    font-size: 1em;
    box-shadow: 0px 0px 2px rgba(0,0,0.4);
    
    transition: 0.2s ease-in-out;
}

input:focus, select:focus {
    box-shadow: inset 1px 1px 3px rgba(0,0,0, 0.3);
}








    

