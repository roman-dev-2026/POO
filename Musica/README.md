# Ejercicio N°5 Musica 16/04/26
## Este es el main de la clase principal que contiene el objetos instanciado de la clase Playlist
```java 

package actividad.pkg05.ejercicio.pkg1;
public class musica {

    public static void main(String[] args) {
        Platlist misFavoritos = new Platlist("Clásicos del Pop");
        
        misFavoritos.agregar(new Cancion("La Flaca", "Jarabe de Palo"));
        misFavoritos.agregar(new Cancion("Color Esperanza", "Diego Torres"));
        misFavoritos.agregar(new Cancion("Ciega, Sordomuda", "Shakira"));
        misFavoritos.agregar(new Cancion("Persiana Americana", "Soda Stereo"));

        System.out.println("--- Mi Playlist de los 90/2000 ---");
        misFavoritos.mostrarPlatlist();
        
    }
    
}

```
## Esta es la subclase (Cancion) de la clase principal que contiene los atributos de la cancion. con sus constructores con y sin parametros y los metodos set y get
```java

public class Cancion {
    private String artista;
    private String cancion;

    public Cancion(String artista, String cancion) {
        this.artista = artista;
        this.cancion = cancion;
    }

    public String getArtista() {
        return artista;
    }

    public String getCancion() {
        return cancion;
    }

    public void setArtista(String artista) {
        this.artista = artista;
    }

    public void setCancion(String cancion) {
        this.cancion = cancion;
    }
    
}

```
## Esta es la subclase (Playlist) que contiene la lista del objeto tipo clase Cancion con sus constructores con y sin parametros y los metodos set y get
```java

package actividad.pkg05.ejercicio.pkg1;
import java.util.ArrayList;
import java.util.List;
public class Platlist {
    private String nombre;
    private List<Cancion> favoritos= new ArrayList<>();

    public Platlist(String nombre) {
        this.nombre = nombre;
    }

    public String getNombre() {
        return nombre;
    }

    public List<Cancion> getFavoritos() {
        return favoritos;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public void setFavoritos(List<Cancion> favoritos) {
        this.favoritos = favoritos;
    }
     
    public void agregar(Cancion cancion){
        favoritos.add(cancion);
    }
    
    public void mostrarPlatlist() {
        for (Cancion c : favoritos) {
            System.out.println("Canción " + c.getCancion());
            System.out.println(" Artista " + c.getArtista());
        }
    }
}

```