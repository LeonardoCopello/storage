<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Somatório</title>
</head>
<body>
    <p id="total">O valor total é:</p>
    <form action="#">
        Insira o valor: <input type="number" id="val"><br><br>
        <button id="acumularValor">Acumula</button>
        <button id="zerarValor">Zerar</button>
    </form>
    
    <script>
        document.getElementById('acumularValor').addEventListener('click', getValue);
        document.getElementById('zerarValor').addEventListener('click', zerarValor);
        let acumulado = 0;

        function getValue() {
            let inputElm = document.getElementById('val').value;
            inputElmInt = Number(inputElm);
            acumulado = acumulado + inputElmInt;
            localStorage.setItem('valor', acumulado);
            mostraValor();   
        }

        function mostraValor() {
            let vlrTotal = localStorage.getItem('valor');
            document.getElementById('total').innerHTML = `O valor total é ${vlrTotal}`;
            document.getElementById('val').value = "";
        }

        function zerarValor(){
           localStorage.clear();
           exibeValorArmazenado();
       }

// -----------------------------------------------


    //     document.getElementById('btAceita').addEventListener('click', acumularValor);
    //     document.getElementById('btZerar').addEventListener('click', zerarValor);
    //     exibeValorArmazenado()
    
    //    function exibeValorArmazenado(){
    //     let total = localStorage.getItem('total');
        
    //     total = Number(total);
                         
    //     document.getElementById('tot').innerHTML = total;
    //    }
    
    //    function acumularValor(){
    //        let valorDigitado = Number(document.getElementById('val').value);
    //        let valorAcumulado = Number(localStorage.getItem('total'));
    //        let soma = valorDigitado + valorAcumulado;
    //        localStorage.setItem('total', soma);
    //        document.getElementById('val').value = '';
    //        exibeValorArmazenado();
    //    }
    
    //    function zerarValor(){
    //        localStorage.clear();
    //        exibeValorArmazenado();
    //    }
    </script>





</body>
</html>
