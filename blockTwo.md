# Context (Teórica)

# Product Context and Product Summary Context
Productos que vtex ya trae pre-definidos 
### Cómo consumir la información del producto
### Product Context
Usa dos cosas importantes useProduct y useProductDispatch
Obtener la info del producto con **useProduct**  
Es una funcion que nos ayuda a mutar o a cambiar la información del contexto con **useProductDispatch**

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
