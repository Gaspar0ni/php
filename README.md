# PHP Comandos

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

## Condicional

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

# Parâmetro por valor e por referência

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

trim(), strlen(), strtolower(), strupper(), str_replace(), substr(), 
