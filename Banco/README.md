# 08/05/26
##
```java
public class Cajeroautomatico {
        static double deposito=0;
        static double cuenta=20000;
        static double retiro=0;
        static double ticket=0;
        static int op=0;
        static double result=0;
    public static void main(String[] args) {
        Cuenta clase2 = new Cuenta();
        Scanner lectura = new Scanner(System.in);
        while(op!=4){
            System.out.println("BIENVENIDO A CAJERO AUTOMATICO");
            System.out.println("1. Para consulta");
            System.out.println("2. Para depositar dinero");
            System.out.println("3. Para retirar dinero");
            System.out.println("4. Para ver ultimos movimientos");
            op=lectura.nextInt();
            switch(op){
                case 1:
                    clase2.getsaldo();
                    break;
                case 2:
                    clase2.Depositar();
                    break;
                case 3:
                    clase2.retiro();
                    break;
                case 4:
                    clase2.salir();
                default:
            }     
        }
    }
}
```
```java
public class Cuenta {
    private double deposito=0;
    private double cuenta=20000;
    private double retiro=0;
    private int op=0;
    Scanner lectura = new Scanner (System.in);
    public Cuenta(){}
    public void getsaldo(){
        System.out.println("Su saldo es: "+ cuenta);
    }
    public void Depositar(){
        System.out.println("Ingrese el monto que desea depositar");
        deposito=lectura.nextDouble();
        cuenta=(cuenta+deposito);
        System.out.println("Su saldo ahora es: "+ cuenta);
    }
    public void retiro(){
        System.out.println("Ingrese el monto que desea retirar");
            retiro=lectura.nextDouble();
            if (retiro<=cuenta){
                cuenta=(cuenta-retiro);
                System.out.println("Su saldo actual es:"+ cuenta); 
            }
            else {
                System.out.println("Su monto es superior al saldo disponible");
        } 
    }
    public void salir(){
        System.out.println("ADIOS");
    }
}
```