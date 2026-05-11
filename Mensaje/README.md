# Ejercicio de mensaje 09/04/26
## Esta es la clase mian principal que contiene los objetos instanciado de la clase Usuario

```java
package mensajes;
public class Mensajes {
    public static void main(String[] args) {
    Usuario ana = new Usuario("ana");
    Usuario beto = new Usuario("Beto");
    Usuario carla = new Usuario("carla");

    System.out.println("--- Iniciando Simulacion---");
    
    ana.enviarMensaje("Hola Beto, ¿tenés el apunte de POO?",beto);
    beto.enviarMensaje("Hola Ana, sí, ahí te lo paso", ana);
    beto.enviarMensaje("Carla, ¿viste que Ana me pidió el apunte?", carla);
    carla.enviarMensaje("Uh, no se lo pases que todavía tiene errores", beto);

    System.out.println("\n--- Buzón de Ana ---");
    ana.verMensajes();

    System.out.println("\n--- Buzón de Beto ---");
    beto.verMensajes();

    System.out.println("\n--- Buzón de Carla ---");
    carla.verMensajes();
    }  
}
```

## Esta es la subclase Usuario con sus atributos con sus constructores con y sin parametros y los metodos set y get

```java
public class Usuario {
    private String nombre;
    private String enviarMensaje;
    private String verMensajes;
    public Usuario(String nombre) {
        this.nombre = nombre;
    }
    
    public String getEnviarMensaje() {
        return enviarMensaje;
    }

    public String getNombre() {
        return nombre;
    }

    public String getVerMensajes() {
        return verMensajes;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public void setEnviarMensaje(String enviarMensaje) {
        this.enviarMensaje = enviarMensaje;
    }

    public void setVerMensajes(String verMensajes) {
        this.verMensajes = verMensajes;
    }
    public void verMensajes(){
        
    }
    public void enviarMensaje(String nombre,Usuario beto){
        
    }
}
```
## esta es la subclase mensaje con sus atributos el constructores con y sin parametros y los metodos set y get

```java
package mensajes;
public class Mensaje {
   private String contenido;
   private Usuario remitente;

    public Mensaje(String contenido, Usuario remitente) {
        this.contenido = contenido;
        this.remitente = remitente;
    }

    public String getContenido() {
        return contenido;
    }

    public Usuario getRemitente() {
        return remitente;
    }

    public void setContenido(String contenido) {
        this.contenido = contenido;
    }

    public void setRemitente(Usuario remitente) {
        this.remitente = remitente;
    }  
}
```