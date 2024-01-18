# 📌 Contador de Clics (Componentes de Clase)
¡Hola! Esta es una aplicación desarrollada con React, un contador de clics interactivo en el cual puedes hacer clic en un botón para incrementar el contador y reiniciar el contador con otro botón. Se usó componentes de clase para explicar cómo convertir componentes funcionales a componentes de clase. 

# Pasos realizados para hacer el cambio de componentes funcinales a componentes de clase

1.- Tenemos que cambiar el componente principal de la aplicación, componente App.js
2.- Tenemos que cambiar el componente Boton.js
3.- Tenemos que cambiar el componente Contador.js

4a.- Componente Contador, escribimos la palabra clave class Contador extends React.Component{
	//metodo obligatorio en los componentes de clase
	render(){
	//lo que devuelve el return de nuestro componente funcional, todo lo que hay a partir de return
	}
}
4b.- Se adaptan los props con {this.props.numClics}

5a.- Componente Boton, 
	class Contador extends React.Component{
		//metodo obligatorio en los componentes de clase
		render(){
		//lo que devuelve el return de nuestro componente funcional, todo lo que hay a partir de return
		}
	}
5b.- Se adapta los props con {this.props.manejarClic}, this.props...


6a.- Componente App.js tenemos que modificar las funciones y pasarlas como metodos
	class App extends React.Component{
		constructor(){
			//hereda toda la funcionalidad de React.Component
			super();
			//definir el estado que sustituye a los hook
			this.state ={
				numClics:0
			}
		}
		render(){
			//codigo jsx que devuelve el componente funcional
		}
	}
	//adaptamos nuestro props de la siguiente manear {this.state.numClics}...

	//metodo manejarClic pasarle una función a setState
	manejarClic(){
		this.setState(({numClics})=> ({ numClics : numClics + 1 }));
	}
	//metodo reiniciarContador
	reiniciarContador(){
		this.setState({ numClics: 0 });
	}

	//para llamar a los metodos tengo que poner this.manejarClic y this.reiniciarContador
	
6b.- Pasar esos métodos a otros componentes
	
	//significado de this, como no hagamos lo siguiente se pierde el contexto.
	//bind asocia el significado de this en el constructor con el this de los métodos.
	this.manejarClic = this.manejarClic.bind(this);
	this.reiniciarContador = this.reiniciarContador.bind(this);


6c.- Tenemos que adaptar el estado y no se trabajan con hook, sino que tenemos que trabajar con un objeto llamado estado.
