# Toastmasters Pachuca - Design Tokens

Este paquete centraliza y distribuye los tokens de diseño (colores, tipografías, gradientes, espaciados y dimensiones) basados en el manual oficial de marca de **Toastmasters International**, configurado y optimizado para los proyectos del club de Pachuca.

---

## 🎨 Paleta de Colores Oficial

Los colores principales de la marca, renderizados a continuación:

| Color | Muestra | Código Hexadecimal | RGB |
| :--- | :---: | :--- | :--- |
| **Loyal Blue** (Principal) | <img src="https://placehold.co/150x50/004165/004165.png" width="150" height="50" alt="Loyal Blue" /> | `#004165` | `0, 65, 101` |
| **True Maroon** (Secundario)| <img src="https://placehold.co/150x50/772432/772432.png" width="150" height="50" alt="True Maroon" /> | `#772432` | `119, 36, 50` |
| **Cool Gray** (Apoyo) | <img src="https://placehold.co/150x50/A9B2B1/A9B2B1.png" width="150" height="50" alt="Cool Gray" /> | `#A9B2B1` | `169, 178, 177` |
| **Happy Yellow** (Acento)| <img src="https://placehold.co/150x50/F2DF74/F2DF74.png" width="150" height="50" alt="Happy Yellow" /> | `#F2DF74` | `242, 223, 116` |

### Gradientes
También incluye el gradiente de la marca de uso frecuente:

| Gradiente | Muestra | Código CSS |
| :--- | :---: | :--- |
| **Loyal to Maroon** | <img src="./assets/loyal-to-maroon-gradient.svg" width="200" height="50" alt="Loyal to Maroon Gradient" /> | `linear-gradient(to right, #004165, #772432)` |

---

## 🔤 Tipografía Autorizada

El sistema de diseño inyecta automáticamente las familias tipográficas oficiales y sus alternativas gratuitas pre-aprobadas:

1. **Titulares (`main`)**: `Gotham` (Alternativa gratuita: `Montserrat`)
2. **Cuerpo de texto (`body`)**: `Myriad Pro` (Alternativa gratuita: `Source Sans 3` / `Source Sans Pro`)
3. **Eventos y Aniversarios (`script`)**: `Corinthia` / `Luxurious Script`

---

## 🛠 Instalación y Uso

Al estar alojado en un repositorio público de GitHub, puedes instalar este paquete directamente en cualquier proyecto Node usando tu gestor de paquetes preferido:

```bash
# Usando npm
npm install VManuelSM/toastmasters-pachuca-design-tokens

# Usando yarn
yarn add VManuelSM/toastmasters-pachuca-design-tokens

# Usando pnpm
pnpm add VManuelSM/toastmasters-pachuca-design-tokens
```

Este repositorio contiene exportaciones listas para usarse tanto en entornos Web (React, Vue, HTML puro) como nativos (React Native).

### Web (`tokens.web.ts`)

Contiene el objeto de JavaScript/TypeScript formateado para la web y un inyector de variables CSS.

```typescript
import { tokensWeb, generateCssVariables } from './tokens.web';

// Acceder a un valor en TS:
console.log(tokensWeb.colors.brand.primary); // "#004165"

// Inyectar en el :root de CSS
const style = document.createElement('style');
style.innerHTML = generateCssVariables();
document.head.appendChild(style);
```

### Nativo (`tokens.native.ts`)

Optimizado para React Native, en donde los sufijos `px` se procesan como números para `StyleSheet` y los gradientes como arreglos.

```typescript
import { tokensNative } from './tokens.native';

const styles = StyleSheet.create({
  container: {
    backgroundColor: tokensNative.colors.brand.primary,
    padding: tokensNative.spacing[4], // 16
    borderRadius: tokensNative.radius.md, // 8
  }
});
```
