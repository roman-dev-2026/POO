# 17/04/26
## Este es el ejercicio de mi equipo de futboll profe jaja
```java
public class Deportes {
    public static void main(String[] args) {
        Equipo miEquipo = new Equipo("Los Programadores F.C.");
        
        miEquipo.fichar(new Jugador("Agustín", "Arquero"));
        miEquipo.fichar(new Jugador("Marcos", "Defensa"));
        miEquipo.fichar(new Jugador("Román", "Delantero"));

        System.out.println("--- Presentación del Equipo ---");
        miEquipo.presentarPlantel();
    }
}
```
## Esta es la clase equipo que contiene la lista de nombres de mis jugadores 
```java
import java.util.ArrayList;
public class Equipo {
    private String nombreEquipo;
    private ArrayList<Jugador> jugador= new ArrayList<>();

    public Equipo(String nombreEquipo) {
        this.nombreEquipo = nombreEquipo;
    }

    public String getNombreEquipo() {
        return nombreEquipo;
    }

    public ArrayList<Jugador> getJugador() {
        return jugador;
    }

    public void setNombreEquipo(String nombreEquipo) {
        this.nombreEquipo = nombreEquipo;
    }

    public void setJugador(ArrayList<Jugador> jugador) {
        this.jugador = jugador;
    }
    
    public void fichar(Jugador jugadores) {
        jugador.add(jugadores);
    }

    public void presentarPlantel() {
        System.out.println("Equipo: " + nombreEquipo);
        for (Jugador c : jugador) {
            System.out.println("Jugador: " + c.getNombre() + " | Posición: " + c.getPosicion());
        }
    }
}
```

```java
public class Jugador {
    private String nombre;
    private String posicion;
    public Jugador(String nombre, String posicion) {
        this.nombre = nombre;
        this.posicion = posicion;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public void setPosicion(String posicion) {
        this.posicion = posicion;
    }

    public String getNombre() {
        return nombre;
    }

    public String getPosicion() {
        return posicion;
    }   
}
```