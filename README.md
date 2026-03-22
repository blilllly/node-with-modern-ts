# Node with modern ts (nodenext)

1. Instalar TypeScript y tipos de Node, como dependencia de desarrollo

```
npm i -D typescript @types/node
```

2. Inicializar el archivo de configuración de TypeScript ( Se puede configurar al gusto)

```
npx tsc --init --outDir dist/ --rootDir src
```

3. Configurar Nodemon y tsx

```
npm install -D tsx nodemon
```

4. Crear archivo de configuración de Nodemon - **nodemon.json**

```
{
  "watch": ["src"],
  "ext": ".ts,.js",
  "ignore": [],
  "exec": "npx tsx ./src/app.ts"
}
```

5. Crear script para correr en desarrollo en el **package.json**

```
  "dev": "nodemon"
```

6. Instalar rimraf (Herramienta que funciona similar al rm -f) eliminar directorio

```
npm install -D rimraf
```

7. Crear scripts en el package.json para construir e iniciar en producción

```
   "build": "rimraf ./dist && tsc",
   "start": "npm run build && node dist/app.js"
```
