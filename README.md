# Estructura-de-datos
Tarea01
package epn;

public abstract class FiguraGeometrica {

	public abstract void calcularArea();
	
	public static void main(String[] args) {
		// TODO Auto-generated method stub
 
	}

}
////////////////////////////////////////////////
package epn;
//Nombre: Alexandra Macas
//Gr1
//Tema:Abstraccion, herencia, encapsulamiento, static
public  class Punto extends FiguraGeometrica {
	private int x;
	private int y; 

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Punto p1 = new Punto(1,5);
		System.out.println("Las coordenadas del punto son:");
		p1.imprimir(p1);
		//System.out.println(p1);
	}

	public int getX() {
		return x;
	}

	public void setX(int x) {
		this.x = x;
	}

	public int getY() {
		return y;
	}


	public void setY(int y) {
		this.y = y;
	}



	public Punto(int x, int y){
		this.x=x;
		this.y=y;
	}

	@Override
	public String toString() {
		return "Punto sus coordenadas son:\n"
				+ " [x=" + x + ", y=" + y + "]";
	}

	public Punto imprimir(Punto p){

		System.out.println(" [x="+x + ", y=" + y + "]");

		return p;

	}

	@Override
	public void calcularArea() {
		// TODO Auto-generated method stub
		Punto p1 = new Punto(getX(), getX());
		Punto p2 = new Punto(getX(), getX());
		double distancia= Math.sqrt(Math.pow(p1.getX()-p2.getY(),2));

	}

	public void calcularArea(Punto p1, Punto p2) {
		// TODO Auto-generated method stub
		double distancia= Math.sqrt(Math.pow(p1.getX()-p2.getX(),2)+ Math.pow(p1.getY()-p2.getY(),2));

		p1.imprimirArea(distancia);
	}

	protected void imprimirArea(double distancia) {
		// TODO Auto-generated method stub
		System.out.println("area: "+distancia);
	}

	/**/
}
//////////////////////////////////////////////////////////
package epn;

public class Rectangulo extends Punto{

	public Rectangulo(int x, int y) {
		super(x, y);
		// TODO Auto-generated constructor stub
	}

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Punto p1 = new Punto(0,3);
		Punto p2 = new Punto(0,5);
		Punto p3 = new Punto(4,3);
		Punto p4 = new Punto(4,5);
		double distancia1= Math.sqrt(Math.pow(p3.getX()-p1.getX(),2));
		double distancia3= Math.sqrt(Math.pow(p4.getX()-p2.getX(),2));
		double distancia2= Math.sqrt( Math.pow(p4.getY()-p3.getY(),2));
		double distancia4= Math.sqrt( Math.pow(p2.getY()-p1.getY(),2));
		if(distancia1!=distancia3&&distancia2!=distancia4){

			System.out.println("No es un rectangulo");
		}
		else
		System.out.println("Las cordenadas del rectangulo  son: \n 1er:");
		p1.imprimir(p1);
		System.out.println("2do:");
		p2.imprimir(p2);
		System.out.println("3ro:");
		p3.imprimir(p3);
		System.out.println("4to:");
		p4.imprimir(p4);
		
		double distanciaT= distancia1*distancia2;
		p1.imprimirArea(distanciaT);
	}

}
////////////////////////////////////////////////////////////////////////
package epn;

public class Cuadrado extends Punto {



	public Cuadrado(int x, int y) {
		super(x, y);
		// TODO Auto-generated constructor stub
	}

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Punto p1 = new Punto(0,2);
		Punto p2 = new Punto(0,4);
		Punto p3 = new Punto(2,2);
		Punto p4 = new Punto(2,4);


		double distancia= Math.sqrt(Math.pow(p1.getX()-p2.getX(),2)+ Math.pow(p1.getY()-p2.getY(),2));
		double distancia2= Math.sqrt(Math.pow(p4.getX()-p3.getX(),2)+ Math.pow(p4.getY()-p3.getY(),2));
		if(distancia!=distancia2){

			System.out.println("No es un cuadrado");
		}
		else
			System.out.println("Las cordenadas del cuadrado  son: \n 1er:");
		p1.imprimir(p1);
		System.out.println("2do:");
		p2.imprimir(p2);
		System.out.println("3ro:");
		p3.imprimir(p3);
		System.out.println("4to:");
		p4.imprimir(p4);


		distancia= distancia*distancia;
		p1.imprimirArea(distancia);

	}




}
////////////////////////////////////////////////////////////
package epn;

public class Circulo  extends Punto{
private double radio;
	
public static void main(String[] args) {
	// TODO Auto-generated method stub
	
	Circulo cir= new Circulo(0, 2, 1.9);
	cir.validacion(cir);
	double distancia=cir.radio*cir.radio*3.1416;
	
	cir.imprimirArea(distancia);

}


public double getRadio() {
	return radio;
}


public void setRadio(double radio) {
	this.radio = radio;
}


	public Circulo(int x, int y, double radio) {
		super(x, y);
		this.radio= radio;
		// TODO Auto-generated constructor stub
	}
	

	
public Circulo imprimir(Circulo p){
		
		System.out.println(" Centro :[x="+p.getX() + ", y=" + p.getY() + "]\n radio: "+ p.getRadio() );
		
		return p;}

	@Override
	public String toString() {
		return "Circulo [radio=" + radio + ", getRadio()=" + getRadio() + "]";
	}
	public void validacion(Circulo cir){
		if(cir.radio<1){
			System.out.println("Error!!! Radio menor o igual que cero");
			
		}
		else
		System.out.println("Las cordenadas del circulo  son:");
		cir.imprimir(cir);
	}

}
///////////////////////////////////////////////////////////////////////
package epn;

public class Linea extends Punto {
	
	

	public Linea(int x, int y) {
		super(x, y);
		
		// TODO Auto-generated constructor stub
	}

	public static void main(String[] args) {
		// TODO Auto-generated method stub
	
		
			
			Punto p1 = new Punto(1,2);
			Punto p2 = new Punto(3, 5);
			System.out.println("Las cordenadas de la lineas son: \n1er:");
			p1.imprimir(p1);
			System.out.println("2do:");
			p2.imprimir(p2);
			//System.out.println(p1);
			
	   
		
	}
	
}




