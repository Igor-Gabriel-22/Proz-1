EXERCÍCIO 1

<?php

$nota1 = readline("digite sua primeira nota: ");

$nota2 = readline("digite sua segunda nota: ");

$nota3 = readline("digite sua terceira nota: ");

$media = ($nota1 + $nota2 + $nota3)/3;

echo "sua media e de $media";


EXERCÍCIO 2

<?php

interface autenticavel {
    public function login(string $usuario, string $senha): bool;
}

class usuariocomum implements autenticavel {
    public function login(string $usuario, string $senha): bool{
        return $usuario != "" && $senha != "";
    }
}

class administrador implements autenticavel {
    public function login(string $usuario, string $senha): bool{
        if ($usuario == "" || strlen($senha) < 8){
            return false;
        }
        
        return true;
    }
}

EXERCÍCIO 3
abstract class metodopagamento {
    protected $valor; 
    
    public function __construct($valor) {
        $this->valor = $valor;
    }
    
    abstract public function processar(): bool;
}

class cartaocredito extends metodopagamento {
    public function processar(): bool {
        $valorfinal = $this->valor - ($this->valor * 0.02); 
        return true;
    }
}

class pix extends metodopagamento {
    public function processar(): bool {
        $valorfinal = $this->valor - ($this->valor * 0.05); 
        return true;
    }
}

EXERCÍCIO 4

class Calculadora {

public $soma;

public $subtracao;

public $multiplicacao;

public $divisao;

public function _ construct($soma, $subtraçao, $multiplicacao, $divisao) {

$this->soma = $soma;

$this->subtracao = $subtracao;

$this->multiplicacao = $multiplicacao;

$this->divisao = $divisao

}



public function calculos(): string {

return "Resultados de $this->soma, $this->subtracao, $this->multiplicacao, $this->divisao sao os resultados."
}

}

EXERCÍCIO 5

<?php

class Livro {
    public $titulo;
    public $autor;
    public $paginas;

    public function __construct($titulo, $autor, $paginas) {
        $this->titulo = $titulo;
        $this->autor = $autor;
        $this->paginas = $paginas;
    }
}

$livro1 = new Livro("O Alquimista", "Paulo Coelho", 172);
$livro2 = new Livro("Dom Casmurro", "Machado de Assis", 256);

echo "Livro 1:\n";
echo "Título: " . $livro1->titulo . "\n";
echo "Autor: " . $livro1->autor . "\n";
echo "Páginas: " . $livro1->paginas . "\n\n";

echo "Livro 2:\n";
echo "Título: " . $livro2->titulo . "\n";
echo "Autor: " . $livro2->autor . "\n";
echo "Páginas: " . $livro2->paginas . "\n";

