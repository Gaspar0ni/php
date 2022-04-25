# PHP Comandos [INTRODUÇÃO]

baixar php, apache, vscode (xamp)

IP direcionando para o computador: 127.0.0.1 (atalho localhost) (seu ip tbm)

<?php echo 'alguma coisa'; ?>

Se difitar: <?php sajIdjaisjdi ?> ele recebe erro de sintaxe;

declarando variáveis: $nome_da_var;

atribuir valor a var: $s = 10;

variáveis com nomes maiores: $nomeDaVariavel

comentários se usa: "//"

as variáveis string aceitam '' ou "";

### Concatenando var

```
<?php 
$nome = "Guilherme";
$sobrenome = "Vimieiro";
echo $nome . " " . $sobrenome;
echo "$nome $sobrenome";
$nomeCompleto = $nome . " " . $sobrenome;
echo $nomeCompleto

$nomeCompleto = $nome;
$nomeCompleto .= " ". $sobrenome;
?>
```

### Arrays:

```
$ingredientes = ['açucar', 'farinha de trigo', 'ovos'];
$echo ingrediente=[0];

foreach($array as $chave => $valor){
    echo “{$chave}: {$valor}\n“;
}


// Definição da chave automaticamente
$notas[] = 'Novo valor';

$myarray = [];
```

Array spread
```
<?php
$bolo1=['açucar', 'ovo', 'leite'];
$bolo2=[...$bolo1, corante];
print_r($bolo2);
```

```
<?php
$lista = [
  'nome' => 'Guilherme',
  'idade' => 90,
  'atributos' => [
      'forca' => 60,
       'agilidae' => 80
    ],
   'vida'= 1000,
   'mana'= 980
];

echo "NOME: ".$lista['nome']."<br>";
echo "FORÇA: "    .$lista['atributos'][forca]."<br>"
echo "VIDA".$lista['vida'];
```

# Condicional e LOOPS

```
<?php
$idade = 0;
if($idade > 18){
  echo "maior idade";
}else{
  echo "menor de idade";
}
```

Ternário
```
$idade = 20;
echo ($idade <18) ? 'menor de idade' : 'maior de idade';
```

NULL CAO

```
<?php
$nome = "Guilherme";

$nomeCompleto = $nome;
$nomeCompleto .= isset($sobrenome) ? sobrenome : '';

echo $nomeCompleto;

ou
$nomeCompleto .= $sobrenome ?? '';
```

Switch PHP (quando é melhor utilizá-lo)

```
<?php
$tipo = 'texto';

switch($topo){
  case foto:
    echo 'Exibindo TEXTO'
    break;
  case 'video'
    echo 'Exibindo video'
    break;
  case 'texto'
    echo 'Exibindo TEXTO'
    break;
}
```

while(){}
```
<?php
$numero = 0;
while($numero <10){
  echo 'N: '.$numero.'<br>';
  $numero += 1;
}

```
<?php
FOR ($numero = 0;$numero <10; $numero +=1){
  echo 'N: '.$numero.'<br>';
}
```

FOREACH (feito para trabalhar com arrays)
```
<?php
$ingredientes = ['açucar', 'farinha de trigo', 'ovos'];
foreach ($ingredientes as $ingrediente){
  echo "Item: ".$ingrediente."<br>";
}

outro

echo '<ul>';
foreach($ingredientes as $valor){
  echo '<li>'.$valor.'</li>';
}
echo '</u>;
```
```
print_r($var);

function nome($parametro, $n1 = 0){
  $paramentro .= 10;
  return ($parametro, int $n1)
}
x = nome(10);
```

# Funções, Parâmetro e includes

Parâmetro por valor e por referência

```
function valor($n1, $n2 = 0, &n3){
  $n3 = $n1 + $n2;
}
$n1=2;
$n2=5;
$soma=0;

valor($n1, $n2, $soma)      //não passou o valor e sim a variável

echo $soma;
```

sort()

----------------------------------------------------------------------

## Funções anônimas

```
<?php
$dizimo = function(int valor){
  return $valor * 0,1;
};
echo $dizimo(90);
$funcao= $dizimo;
echo funcao(82);

$r = function(){};
```

## arroy function -> só pode conter uma expressão:

$dizimo = fn($valor) => valor * 0,1;

---------------------------------------------------------------------------

função recursiva

```
<?php
function dividir($numero){
  $metade = $numero /2;
  echo $metade."<br>";
  
  if($metade > 0){
    dividir($metade);
}
```

### Funções matemáticas: round(), abs(), pi(), floor(), ceil(), rand(), max(), min(), 

[Funções Matemáticas](https://www.php.net/manual/en/ref.math.php)

### Funções para string

trim(), strlen(), strtolower(), strupper(), str_replace(), substr(), strpos(), ucFirst(), ucwords(), explode() *****,implode(), number_format(),
 
### Funções para arrays

count(), array_diff(), array_filter(), array_map(), array_pop(), array_shift(), if(in_array()){}, array_search(), sort(), rsort(), asort(), arsort(), 

### Data Hora   [Funções Data](https://www.php.net/manual/pt_BR/refs.calendar.php)

time(), date('d/m/Y' H:i:s), strtotime(), 

```
<?php
$showDate = function($inputDate) {
    setlocale(LC_TIME, 'pt_BR', 'pt_BR.utf-8', 'pt_BR.utf-8', 'portuguese');
   
    echo strftime('%A, %d de %B de %Y', strtotime($inputDate));
    echo $showDate('1971-01-02');
};
```

require() e include(), require_once(), @include_once(), @require_once(), require(./template/header.php)           o "./" acessa a mesma pasta



------------------------------------------------------------------------------------------------
# MOD 4 - Formulário, Validação, Sessão e Arquivos

http request -> <form method="post" action="recebedor.php">

Métodos mais comuns: GET, POST, PUT, 

# Pegar informações do usuário via tag FORM ->(filter_input(INPUT_GET, 'nome'); **************************************************************************

```
<?php
$nome = filter_input(INPUT_POST, 'nome', FILTER_SANITIZE_SPECIAL_CAHRS);        //da pra fazer por POST também;
$email = filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL);
$idade = filter_input(INPUT_POST, 'idade', FILTER_SANITIZE_NUMBER_INT);         //poderia trocar por FILTER_VALIDATE_INT
if($nome && email && $idade){
    echo 'NOME: '.$nome;
}else{
    header("Location: index.php);
    exit;
}
```

Não tenta limpar para validar

FILTER_VALIDATE_EMAIL, FILTER_VALIDATE_FLOAT, FILTER_VALIDATE_INT, FILTER_VALIDATE_IP, FILTER_VALIDATE_URL

Tenta limpar o código para ser validado

FILTER_SANITIZE_EMAIL, FILTER_SANITIZE_STRING, FILTER_SANITIZE_SPECIAL_CAHRS, FILTER_SANITIZE_URL, FILTER_SANITIZE_NUBER_IT FILTER_SANITIZE_NUMBER_FLOAT

filter_var;

## Sessões

session_start(), $_SESSION

### Cookies no PHP

deve ser setado antes de modificar variáveis

```
$expiracao = time() + (86400 * 30)          //duração de 30 dias

setcookie('nome', $nome, $expiracao);

Na pagoina

<?php
if(isset($_COOKIE['nome'])){
    $nome = $_COOKIE['nome'];
    echo '<h2>.$nome.'</h2>';
}
```

Deletar cookie
setcookie('nome', '', time() - 3600);
```

Lendo arquivo

```
<?php
$texto = file_get_contents('texto.txt');
echo $texto;
$texto = explode("\n", $texto)
echo "LINHAS: ".count($texto);
```

### Escrevendo em arquivos

```
<?php
$texto = "Guilherme Vimieiro";
file_put_contents('nome.txt', $texto);
echo 'arquivo criado com sucesso';
```

### Excluindo arquivo

unlink('lista.txt');        //apenas arquivos, pasta não, pasta é outro comando
echo 'Arquivo excluido com sucesso';

### Movendo e renomeando arquivo

```
<?php
rename('texto.txt', '/pasta/teste2.txt');   //renomeia e muda o diretório do arquivo
copy ('/pasta/teste2.txt', 'texto.txt');    //copia o arquivo e muda o diretório dele

```

### Upload de arquivo

QUando tem arquivo usa se o enctype="multipart/form-data"

```
<?php
<form method="POST" action="recebedor.php" enctype="multipart/form-data">
    <input type="file" name="arquivo">
    <input type="submit" value="ENviar">
</form>


recebedor.php\/ 
echo '<pre>'
print-r($_FILES);

$nome = $_FILES['arquivo']['name'];
move_uploaded_file($_FILES['arquivo']['tmp_name'], 'arquivos/'.$nome);          // CUIDADO SE TIVER 2 ARQUVIOS COM O MESMO NOME ELE SOBREPOE O ARQUIVO ANTERIOR*****
```

```
### UPLOAD de arquivo

echo '<pre>'
print-r($_FILES);

$nome = md5(time().rand(0, 1000).'jpg';
move_uploaded_file($_FILES['arquivo']['tmp_name'], 'arquivos/'.$nome);          // CUIDADO SE TIVER 2 ARQUVIOS COM O MESMO NOME ELE SOBREPOE O ARQUIVO ANTERIOR*****

```

```
echo '<pre>'
print-r($_FILES);

$permitidos = ['imagem.jpeg, 'imagem.jpg', 'imagem.png'];

if(in_array($_FILES['arquivo']['type'], $permitidos)){
    $nome = md5(time().rand(0, 1000).'jpg';
    move_uploaded_file($_FILES['arquivo']['tmp_name'], 'arquivos/'.$nome);

    echo 'Arquivo salvo com sucesso';
}else{
    echo 'arquivo ou extensão não permitidos.';
}
```

# MOD5 - Manipulação de arquivos

```
$array = range(1, 20);
$array = range(1, 20, 2);
$array = range('a', 'g');
$array = range(50, 20, 2);
```

array_keys(), array_values()

arrays verticais e horizontais, array_slice(), array_splice, array_reduce(), 
