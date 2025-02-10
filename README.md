# javaTester
public class ExemploExcecao {
    public static void main (String[] args){
        System.out.print("Entre com uma senha: ");
        String senha = "12345a";
        
        try{
            validarSenha (senha);
            System.out.println("Senha Válida!");
            
        }catch (SenhaInvalidaExcecao e){
            System.out.println("Senha inválida : " + e.getMessage());
        }
    }
    public static void validarSenha(String senha) throws SenhaInvalidaExcecao {
        if (senha.length() < 5) {
            throw new SenhaInvalidaExcecao("A senha deve ter, pelo menos, 5 caracteres.");
        }
        if (!senha.matches(".*\\d.*")){
            throw new SenhaInvalidaExcecao("A senha deve conter, no mínimo, 1 dígito.");
        }
    }
}
class SenhaInvalidaExcecao extends Exception {
    public SenhaInvalidaExcecao(String message){
        super(message);
    }
}
