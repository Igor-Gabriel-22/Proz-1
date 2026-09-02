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


