# 17/05/26
## Ejercicio de albun de fotos
```java
public class AlbunDeFotos {

    public static void main(String[] args) {
        Album verano = new Album("Viaje 2026");
        
        verano.agregarFoto(new Foto("playa.jpg", 4.5f));
        verano.agregarFoto(new Foto("familia.png", 3.2f));
        verano.agregarFoto(new Foto("atardecer.jpg", 5.1f));

        System.out.println("--- Galería del Álbum ---");
        verano.verGaleria();
    }   
}
```
```java
public class Foto {
    private String archivo;
    private float espacioMB;

    public Foto(String archivo, float espacioMB) {
        this.archivo = archivo;
        this.espacioMB = espacioMB;
    }

    public void setArchivo(String archivo) {
        this.archivo = archivo;
    }

    public void setEspacioMB(float espacioMB) {
        this.espacioMB = espacioMB;
    }

    public String getArchivo() {
        return archivo;
    }

    public float getEspacioMB() {
        return espacioMB;
    }    
}
```
```java
import java.util.ArrayList;

public class Album {
    private String titulo;
    private  ArrayList<Foto> fotos = new ArrayList<>();

    public Album(String titulo) {
        this.titulo = titulo;
    }

    public String getTitulo() {
        return titulo;
    }

    public ArrayList<Foto> getFotos() {
        return fotos;
    }

    public void setTitulo(String titulo) {
        this.titulo = titulo;
    }

    public void setFotos(ArrayList<Foto> fotos) {
        this.fotos = fotos;
    }
    
    public void agregarFoto(Foto foto) {
        fotos.add(foto);
    }

    public void verGaleria() {
        for (Foto foto : fotos) {
            System.out.println(foto.getArchivo());
        }
    }
}
```