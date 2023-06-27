# Context (Teórica)
VTEX permite crear y administrar múltiples contextos, cada uno de los cuales representa un conjunto de configuraciones específicas.   
# Product Context and Product Summary Context
Se refiere a dos tipos de contexto relacionados con la visualización de productos. Estos contextos permiten personalizar la forma en que se presentan y se muestran los productos a los clientes.  

## Product Context
Se refiere al conjunto de información y configuraciones específicas asociadas a un producto individual. Nos da toda la información del producto, esto incluye detalles como el título del producto, su descripción, imagenes, variantes(color, talla), precios, disponibilidad, sku.  

Dentro del contexto *Product Context* existen los hooks *useProduct* y *useProductDispatch*  
Estos hooks son proporcionados por la biblioteca de VTEX llamada `vtex.product-context`

### **useProduct**  
Este hook se utiliza para acceder a la información del producto y su estado en una aplicación. Proporciona un objeto con los datos del producto, su ID, variantes, atributos y otra información relevante. Al utilizar este hook, puedes obtener y utilizar la información del producto en tu aplicación para mostrar detalles, realizar cálculos o tomar decisiones basadas en los datos del producto.

### **useProductDispatch**
Este hook se utiliza para realizar acciones relacionadas con el producto, como agregar o quitar productos del carrito, cambiar la cantidad de productos, seleccionar variantes o realizar otras operaciones relacionadas con el producto. El useProductDispatch se utiliza en combinación con useProduct para realizar cambios en el estado del producto y reflejar esos cambios en la interfaz de usuario.  

## Product Summary Context
Se refiere a la información resumida de un producto, este contexto se utiliza para mostar productos de manera más compacta como en listas de resultados de busqueda, páginas de categorías, widgets.  

En resumen, el **Product Context** se utiliza para mostrar información más detallada de un producto en la página de detalles mientras que **Product Summary Context**  se utiliza para mostrar una vista resumida de los productos en listas o widgets.

# Search Context 
El search context es el contexto en el que funcionan todas nuestras páginas de categoría, departamento, resultados de busqueda y esa información quedara guardada en  el search context por lo que renderiza los componentes de la busqueda funcionan dependiendo del contexto 

### Hooks para trabajar con context
```
import {
  useSearchPageState,
  useSearchPage,
  useSearchPageStateDispatch,
} from 'vtex.search-page-context/SearchPageContext'

```
**useSearchPageState**  
Nos devuelve un objeto con información de como esta funcionando nuestro resultado de busqueda 

**useSearchPage**  
Nos devuelve un objeto con toda la información con la que se construyen los componentes, la data de los productos que se muestran en la busqueda, especificaciones de producto

**useSearchPageStateDispatch**  
El dispatch nos va a permitir enviar ciertos eventos para modificar algo de la construcción de nuestro resultado de busqueda
El dispatch nos recibe cierto tipo de evento y en base a eso ejecuta una acción dentro de nuestro contexto

```
const dispatchExample = () => {
  const dispatch = useSearchPageStateDispatch()
  return (
    <div>
      <button
        variation: 'primary',
        onClick: {() => {
          dispatch:({
            type: 'SWITCH_GALLERY_LAYOUT'
            args: {selectedGalleryLayout: 'grid'}
            })
          }} 
      >Primary<button>
    </div>
  )
}
```

# Info Card List Context


