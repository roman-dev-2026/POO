#  Juego 25/03/26
## Esta es la clase main principal. contiene la instancia de los objetos de la clase Personaje

```java
package juego;
import java.util.Scanner;
public class Juego {
    public static void main(String[] args) {
        Scanner lectura = new Scanner (System.in);
        Personaje roman = new Personaje();
        Personaje agustin = new Personaje();
        Personaje nacho = new Personaje("nacho",100,0);
        Personaje jugador4 = new Personaje("pikachu", 100, 0);
        roman.setNombre("ROMAN");
        roman.setVida(100);
        roman.setAtaque(0);
        agustin.setNombre("agustin");
        agustin.setVida(100);
        agustin.setAtaque(0);
        roman.atacar(nacho);
        nacho.atacar(agustin);
        agustin.atacar(nacho);
        roman.curar(agustin);
        nacho.curar(roman);
        System.out.println("JUGADOR: 1 "+roman.getNombre()+" Vida  "+roman.getVida() +" Ataque "+ roman.getAtaque());
        System.out.println("JUGADOR: 2 "+ agustin.getNombre()+" Vida "+agustin.getVida()+" Ataque "+agustin.getAtaque());
        System.out.println("JUGADOR: 3 "+ nacho.getNombre()+" Vida "+nacho.getVida()+" Ataque "+nacho.getAtaque());
        System.out.println("JUGADOR: 4 "+ jugador4.getNombre()+" Vida "+jugador4.getVida()+" Ataque "+jugador4.getAtaque());   
    }   
}
```
## Esta es la subclase Personajes con sus atributos. constructores con y sin parametros con sus respectivos metodos get y set
```java
package juego;
import java.util.Scanner;

public class Personaje {
    private String nombre="";
    private int vida=0;
    private int ataque=0;
    Scanner lectura = new Scanner (System.in);
    public Personaje() {
    }
    
    public Personaje(String nombre, int vida, int ataque){
        this.nombre = nombre;
        this.vida = vida;
        this.ataque = ataque;
    }
    
    public String getNombre() {
        return nombre;
    }

    public int getVida() {
        return vida;
    }

    public int getAtaque() {
        return ataque;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public void setVida(int vida) {
        this.vida = vida;
    }

    public void setAtaque(int ataque) {
        this.ataque = ataque;
    }
    
    public void curar(Personaje roman){
        int curar=0;
        System.out.println("ingrese la vida que quiere cargar");
        curar=lectura.nextInt();
        roman.setVida(roman.getVida() + curar);
    }
    
    public void atacar(Personaje personaje){
        System.out.println("cuantos puntos desea quitar");
        ataque=lectura.nextInt();
        personaje.setVida(personaje.getVida() - ataque);
    }    
}
```