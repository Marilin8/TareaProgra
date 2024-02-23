# TareaProgra

Este repositorio contiene una implementación de una lista simplemente enlazada en Java. 
Las listas simplemente enlazadas son estructuras de datos lineales donde cada elemento, llamdo nodo, contien un valor y una referencia al siguiente nodo en la secuencia. Estas listas se utilizan para almacenar y manipular datos de manera dinámica, nos permite insertar y eliminar en cualquier posición.

La lista permite realizar las siguientes operaciones:
Insertar: Puedes agregar elementos al inicio, al final o en una posición específica de la lista.

  Para agregar un nodo al inicio de la lista escribimos las siguientes líneas de código:
      public void insertarAlinicio(int dato) {
	    Nodo nuevoNodo = new Nodo(dato); //Crea un nuevo nodo con el valor proporcionado
	    nuevoNodo.siguiente = cabeza;//Establece el siguiente de nuevo nodo como la cabeza actual
	    cabeza = nuevoNodo;//Actualiza la cabeza para que apunte al nuevo nodo
       }
  Para insertar un nuevo nodo al final de la lista escribimos las siguientes líneas de código:
      public void insertarAlfinal(int dato) {
	    Nodo nuevoNodo = new Nodo(dato);
	    if (cabeza == null) {//verifica al final de la lista vacia
  		cabeza = nuevoNodo;//Si esta vacia, el nuevo nodo se convierte en la cabeza
	    }else {
		  Nodo temp = cabeza;
	  	while (temp.siguiente !=null) {//Avanza hasta el ultimo nodo de la lista
			temp = temp.siguiente;
  		}
	  	temp.siguiente = nuevoNodo;//Establecer el siguiente del ultimo nodo como el nuevo nodo
  	  }
      }
  Para insertar un nuevo nodo en una posicion especifica de la lista escribimos las siguientes líneas de código:
      public void insertarEnPosicion(int dato, int posicion) {
	    if (posicion < 0) {//verifica si la posicion es valida
		  System.out.println("La posicion debe ser un numero positivo");
	  	return;
    	}
	    if (posicion == 0) {//Inserta al inicio si la possicion es cero
		  insertarAlinicio(dato);
		  return;
	    }
    	Nodo nuevoNodo = new Nodo(dato);
	    Nodo temp = cabeza;
    	for (int i = 0; i < posicion - 1; i++) {//Avanza hasta la posicion anterior a la deseada
	  	if (temp == null) {
			System.out.println("La lista no tiene sufucientes elementos");
			return;
	  	}
		  temp = temp.siguiente;
	    }
	   if(temp == null) {
		  System.out.println("La lista no tiene suficientes elementos");
	  	return;
  	}
	  nuevoNodo.siguiente = temp.siguiente;//Inserta el nuevo nodo en la posicion especificada
	  temp.siguiente = nuevoNodo;
    }
    
Eliminar: Se pueden eliminar elementos de la lista.

  Para ello, escribimos las siguientes líneas de código:
      public void eliminarPrimero() {
	    if (cabeza != null) {//Verifica si la lista no esta vacia
		  cabeza = cabeza.siguiente;//La cabeza se mueve al siguiente nodo
	    }else {
		  System.out.println("La lista esta vacia");	
	    }
      }
	    public void eliminarUltimo() {
		  if (cabeza == null) {
			System.out.println("La lista esta vacia");
			return;
	  	}
	  if (cabeza.siguiente == null) {//verifica si la lista tiene un elemento
		cabeza = null;//Si es asi, la lista queda vacia
		return;
	  }
  	Nodo temp = cabeza;
	  while (temp.siguiente.siguiente !=null) {//Avanza hasta el ultimo penultimo nodo
		temp = temp.siguiente;
  	}
	  temp.siguiente = null;//Elimina la referencia al ultimo nodo
  }
    //Metodo para eliminar un nodo en una posicion especifica de la lista
    public void eliminarEnPosicion(int posicion) {
	  if (posicion < 0) {//Verifica si la posicion es valida
		System.out.println("La posicion debe tener un numero positivo");
		return;
	  }
  	if(posicion == 0) {//Elimina el primer nodo si la posicion es de cero
		eliminarPrimero();
		return;
	  }
	  Nodo temp = cabeza;
  	for (int i = 0; temp !=null && i < posicion - 1; i++) {//Avanza hasta la posicion anterior al nodo a eliminar
		temp = temp.siguiente;
  	}
	  if(temp == null || temp.siguiente == null) {//verifica si la posicion es valida
		System.out.println("La lista no tiene suficientes elementos");
		return;
	  }
	  temp.siguiente = temp.siguiente.siguiente;//Elimina el nodo en la posicion especificada
    }

Buscar: Puedes buscar elementos dentro de la lista.
  Para ello, escribimos las siguientes líneas de código:
      public boolean buscar(int dato) {
	    Nodo temp = cabeza;
	    while (temp != null) {//Recorre la lista
		  if (temp.dato == dato) {//Compara el valor del nodo con el dato buscado
			return true;//Retorna true si lo encuentra
		  }
		  temp = temp.siguiente;
	    }
	    return false;//retorna false si no lo encuentra
      }

Imprimir: La lista puede imprimirse en su totalidad.
  Para ello, escribimos las siguientes líneas de código:
      public void imprimirLista() {
	    Nodo temp = cabeza;
	    System.out.print("Lista: ");
	    while (temp != null) {//Recorre la lista
		  System.out.print(temp.dato + " ");//Imprime el valor del nodo actual
		  temp = temp.siguiente;//Avanza al siguiente nodo
	    }
	    System.out.println();
      }
      
La lista simplemente enlazada ofrece una estructura de datos simple pero versátil que es ideal para comprender los conceptos básicos de las estructuras enlazadas. 
