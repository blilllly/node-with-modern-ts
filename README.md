# Node with modern ts (nodenext)

1. Instalar TypeScript y las demas dependencias

```
npm i -D typescript @types/node tsx nodemon rimraf
```

2. Inicializar el archivo de configuración de TypeScript ( Se puede configurar al gusto)

```
npx tsc --init --outDir dist/ --rootDir src
```

3. Crear archivo de configuración de Nodemon - **nodemon.json**

```
{
  "watch": ["src"],
  "ext": ".ts,.js",
  "ignore": [],
  "exec": "npx tsx ./src/app.ts"
}
```

4. Crear scripts en el package.json para construir e iniciar en producción

```
  "dev": "nodemon"
  "build": "rimraf ./dist && tsc",
  "start": "npm run build && node dist/app.js"
```
