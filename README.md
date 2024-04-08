# Explicacion
Nombre: Marco Enriquez
Fecha: 07-04-2024
Ciclo: Tercero
Carrera: Desarrollo de software
Materia: Programación de aplicaciones móviles 
Ingeniero: Jonathan Vallejo
Descripción de ejercicios de Exercism 1 y 2
1-Primer ejercicio TwoFer
En este ejercicio cambie la forma de como debe de ser vista ya que lo pasamos de Excercism: 
 
A react: Agregando cada información en un componente 
App.tsx
import TwoFer from './TwoFer'; 

function App() {
  return (
    <div>
      <h1>Welcome to My App</h1>
      <TwoFer /> {"One for you, one for me." }
      <TwoFer name="Alice" /> {  "One for Alice, one for me"}
      <TwoFer name="Bob" /> { "One for Bob, one for me." }
    </div>
  );
}

export default App;

TwoFer.d.ts
import { FunctionComponent } from "react";

declare const TwoFer: FunctionComponent<{ name?: string }>;
export default TwoFer;


TwoFer.tsx

function TwoFer({ name = "you" }) {
  return <p>One for {name}, one for me.</p>;
}

export default TwoFer;


vite-env.s.ts

declare module './TwoFer' {
    import { FunctionComponent } from 'react';
  
    const TwoFer: FunctionComponent<{ name?: string }>;
    export default TwoFer;
  }
  

Cómo se logra observar he creado dos nuevos componentes llamados TwoFer.d.Ts y otro componente llamado TwoFer.tsx en el que se logra observar el código que está ligado en cada uno de los componentes ya mencionados, qué hace que la página pueda leer el código mencionado en cada uno de los componentes para que así se logre inicializar en el componente de app.tsx en el que dará un resultado de en la página de localhost nos da un resultado de welcome to my My app y se logra observar los siguientes ejemplos que se lograrán observar a continuación.

1.	Definición del componente App:
•	Creamos un componente funcional llamado App que devuelve elementos JSX representando la estructura de nuestra aplicación. Incluye un encabezado (<h1>Welcome to My App</h1>) y tres instancias del componente TwoFer con diferentes nombres pasados como propiedades (name).
2.	Exportación del componente App:
•	Exportamos el componente App para que pueda ser importado y utilizado en otros archivos de nuestra aplicación.
3.	Uso del componente TwoFer:
•	Renderizamos tres instancias del componente TwoFer dentro del componente App. Cada instancia muestra el mensaje "One for {name}, one for me." con un nombre diferente o el valor predeterminado "you" si no se proporciona ningún nombre

 
Nos da como resultado la imagen ya mostrada, esto ayuda más bien que los componentes que fueron mencionados tengan una función que haga que el componente principal los lea detenidamente sin que haya ningún tipo de error ya que Vite se encarga de que haya un inicio de desarrollo increíblemente rápido para compilar y servir el código de forma eficiente durante el desarrollo.
2-Ejercicio Resistor Color.
Ahora en este ejercicio será lo mismo en exercism:
 
Pero sin la necesidad de crear un componente ya que solo son colores, no necesitamos importar nada adicional, ya que estamos usando las constantes y tipos que definimos en el mismo archivo.
export const COLORS = [
  'black',
  'brown',
  'red',
  'orange',
  'yellow',
  'green',
  'blue',
  'violet',
  'grey',
  'white',
] as const;

type Colors = typeof COLORS[number];

export const colorCode = (color: Colors) => COLORS.indexOf(color);

function App() {
  return (
    <div>
      <h1>Color Code</h1>
      <ul>
        {COLORS.map((color, index) => (
          <li key={index}>{color}: {colorCode(color)}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;

Se crea una función llamado App que devolverá la lista de colores este código lo renderizará junto con sus códigos de color en el navegador.
 



