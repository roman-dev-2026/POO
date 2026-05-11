# 15/04/26
## Ejercicio de notas de un alumno de la escuela
```java
public class EscuelaPrimaria {
    public static void main(String[] args) {
        Alumno ana = new Alumno("Ana");
        Alumno beto = new Alumno("Beto");
        Alumno carla = new Alumno("Carla");

        Maestro juan = new Maestro("Juan", "4to Grado");

        System.out.println("--- Iniciando Simulación de Evaluación ---");

        juan.calificar(ana, new Nota(9, "Matemática"));
        juan.calificar(beto, new Nota(8, "Lengua"));
        juan.calificar(carla, new Nota(7, "Matemática"));

        System.out.println("\n--- Resultados Finales ---");
        System.out.println("calficación de ana");
        ana.verNotas();
        System.out.println("calificación de beto");
        beto.verNotas();
        System.out.println("calificación de ");
        carla.verNotas();
    }   
}
```
## Estas son sus clases (todavia no vimos herencia ni nada solo instancias). La clase alumno con sus atributos. metodos y constructores
```java
import java.util.ArrayList;
import java.util.List;

public class Alumno {
    private String nombre;
    private List<Nota> notas = new ArrayList<>();

    public Alumno(String nombre) {
        this.nombre = nombre;
        
    }

    public String getNombre() {
        return nombre;
    }

    public List<Nota> getNotas() {
        return notas;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public void setNotas(List<Nota> notas) {
        this.notas = notas;
    }

    public void agregarNota(Nota nota) {
        notas.add(nota);
    }

    public void verNotas() {
        for (Nota nota : notas) {
            System.out.println(" Notas de " + nota.getValor() +" :"+ nota.getMateria());
        }
    }
}
```
## La clase Maestro con sus atributos. metodos y constructores
```java
public class Maestro {
    private String nombre;
    private String grado;

    public Maestro(String nombre, String grado) {
        this.nombre = nombre;
        this.grado = grado;
    }

    public String getNombre() {
        return nombre;
    }

    public String getGrado() {
        return grado;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public void setGrado(String grado) {
        this.grado = grado;
    }

    public void calificar(Alumno evaluado, Nota calif){
        evaluado.agregarNota(calif);
    }
    
}
```
## La clase Nota con sus atributos. metodos y constructores
```java
public class Nota {
    private int valor;
    private String materia;

    public Nota(int valor, String materia) {
        this.valor = valor;
        this.materia = materia;
    }

    public int getValor() {
        return valor;
    }

    public String getMateria() {
        return materia;
    }

    public void setValor(int valor) {
        this.valor = valor;
    }

    public void setMateria(String materia) {
        this.materia = materia;
    }    
}
```