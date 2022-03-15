<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Somatório</title>
    </head>
    <body>
        <form action="soma.php" method="post">
            <p>Total: <span id="tot">0</span></p>
            <p>
                Valor: <input type="number" id="val">
            </p>
            <input type="button" id="btAceita" value="Aceitar">
            <input type="button" id="btZerar" value="Zerar" >
        </form>
	</body>
    <script>

        document.getElementById('btAceita').addEventListener('click', acumularValor);
        document.getElementById('btZerar').addEventListener('click', zerarValor);
        exibeValorArmazenado()

       function exibeValorArmazenado(){
        let total = localStorage.getItem('total');
        
        total = Number(total);
        //total = total == null ? 0 : total;
        //if (total == null) total = 0;
        
        //console.log(total);
        document.getElementById('tot').innerHTML = total;
       }

       function acumularValor(){
           let valorDigitado = Number(document.getElementById('val').value);
           let valorAcumulado = Number(localStorage.getItem('total'));
           let soma = valorDigitado + valorAcumulado;
           localStorage.setItem('total', soma);
           document.getElementById('val').value = '';
           exibeValorArmazenado();
       }

       function zerarValor(){
           localStorage.clear();
           exibeValorArmazenado();
       }
    </script>
</html>
