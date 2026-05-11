# 23/04/26
# Ejercicio de Ferreteria. en este ejecicio tenemos que crear una clase para padre para las demas clases(hijas) llamada Producto, con sus atributos que hereden las clases. con sus respectivas atributos y metodos

## Este es la clase Main que contiene los objetos de tipo clases mediante instancias.
```java
package ferreteria.herencia;

public class FerreteriaHerencia {

    public static void main(String[] args) {
        Herramientas h1 = new Herramientas("0003", "Martillo de Galpón", 101, "Stanley", "Grande");
        Herramientas h2 = new Herramientas("0001", "francesa", 100, "luoqtuff", "mediano");

        InsumoElectrico i1 = new InsumoElectrico("0002", "llave", 0, 0, 0, true);

        Herraje her1 = new Herraje("Acero Inoxidable", "50mm x 50mm", "0004", "Bisagra Reforzada", 890.0);

        System.out.println("--- Inventario de Ferretería Cargado ---");
        System.out.println("Producto: " + h1.getNombre() + " | Marca: " + h1.getMarca());
        System.out.println("Producto: " + i1.getNombre() + " | Voltaje: " + i1.getVoltaje() + "v");
        System.out.println("Producto: " + her1.getNombre() + " | Material: " + her1.getMaterial());
    }  
}
```
## Esta es la clase padre con sus atributos, metodos y constructores 
```java
package ferreteria.herencia;
public class Producto {
    protected String codigo;
    protected String nombre;
    protected double precio;
    public Producto() {
    }

    public Producto(String codigo, String nombre, double precio) {
        this.codigo = codigo;
        this.nombre = nombre;
        this.precio = precio;
    }

    public void setCodigo(String codigo) {
        this.codigo = codigo;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public void setPrecio(double precio) {
        this.precio = precio;
    }

    public String getCodigo() {
        return codigo;
    }

    public String getNombre() {
        return nombre;
    }

    public double getPrecio() {
        return precio;
    }
}
```
# Estas son sus clases hijas
```java
public class InsumoElectrico extends Producto{
    private int voltaje;
    private int amperaje;
    private boolean escertificado;
    public InsumoElectrico(String codigo, String nombre, double precio, int voltaje, int amperaje, boolean escertificado) {
        super(codigo, nombre, precio);
        this.voltaje = voltaje;
        this.amperaje = amperaje;
        this.escertificado = escertificado;
    }

    public int getVoltaje() {
        return voltaje;
    }

    public int getAmperaje() {
        return amperaje;
    }

    public boolean isEscertificado() {
        return escertificado;
    }

    public void setVoltaje(int voltaje) {
        this.voltaje = voltaje;
    }

    public void setAmperaje(int amperaje) {
        this.amperaje = amperaje;
    }

    public void setEscertificado(boolean escertificado) {
        this.escertificado = escertificado;
    }   
}
```

```java
public class Herramientas extends Producto{
    private String marca;
    private String tamaño;

    public Herramientas(String codigo, String nombre, double precio, String marca, String tamaño) {
        super(codigo, nombre, precio);
        this.marca = marca;
        this.marca = marca;
    }
    
    public String getMarca() {
        return marca;
    }

    public String getTamaño() {
        return tamaño;
    }

    public void setMarca(String marca) {
        this.marca = marca;
    }

    public void setTamaño(String tamaño) {
        this.tamaño = tamaño;
    } 
}
```

```java
public class Herraje extends Producto{
    private String dimensiones;
    private String material;

    public Herraje(String dimensiones, String material, String codigo, String nombre, double precio) {
        super(codigo, nombre, precio);
        this.dimensiones = dimensiones;
        this.material = material;
    }

    public String getDimensiones() {
        return dimensiones;
    }

    public String getMaterial() {
        return material;
    }

    public void setDimensiones(String dimensiones) {
        this.dimensiones = dimensiones;
    }

    public void setMaterial(String material) {
        this.material = material;
    }  
}
```