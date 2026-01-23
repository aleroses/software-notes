# Probar proyecto desde la red local

Problema:
- Probar un proyecto en desarrollo desde cualquier dispositivo conectado a la misma red local.

Solución:
- Usar IP local
- Ejecutar Vite con `-- --host`

## Obtener IP

Tu celular y tu PC deben estar **conectados a la misma red**.

```bash
ip a
```

```bash
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: enp4s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 3c:7c:3f:17:0b:c6 brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.186/24👈🏼👀🔥 brd 192.168.0.255 scope global dynamic noprefixroute enp4s0
       valid_lft 4764sec preferred_lft 4764sec
    inet6 fe80::3e7c:3fff:fe17:bc6/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
```

Lo que necesitas:

```bash
192.168.0.186
```

## Arrancar Vite escuchando la red

Ahora en tu proyecto en este caso usando React + Vite:

```bash
npm run dev -- --host
```

O si usas `pnpm` / `yarn`:

```bash
pnpm dev -- --host
# o 
yarn dev --host
```

Deberías ver algo como:

```bash
> tic-tac-toe@0.0.0 dev
> vite --host


  VITE v6.2.3  ready in 186 ms

  ➜  Local:   http://localhost:5173/tic-tac-toe/
  ➜  Network: http://192.168.1.186:5173/tic-tac-toe/
  ➜  press h + enter to show help
```

## Abre la app en tu celular

En el navegador del celular escribe **exactamente**:

```bash
http://192.168.1.186:5173/tic-tac-toe/
```

## ⭐ Tip para desarrollo

Si quieres que **siempre** esté disponible sin flags `-- --host`:

`vite.config.ts`

```ts
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react-swc';

// https://vite.dev/config/
export default defineConfig({
  plugins: [react()],
  base: '/tic-tac-toe/',
  server: { // 👈🏼👀
    host: true,
  },
});
```

✅ Con esto puedes hacer solo:

`npm run dev`

Y listo.

## Usando Live Server

La extensión Live Server para VS Code es una herramienta esencial que lanza un servidor de desarrollo local, permitiendo previsualizar proyectos web con una **recarga automática en tiempo real en el navegador** cada vez que guardas cambios en tu código HTML, CSS o JavaScript, eliminando la necesidad de refrescar la página manualmente y agilizando el flujo de trabajo.

Para usarlo debes hacer:

- **Clic derecho** dentro de tu `HTML`
- Elegir **Open with Live Server**

Te da algo así:

```
http://127.0.0.1:5500/index.html
```

Modifícalo y pégalo en tu móvil:

```bash
http://192.168.1.186:5500/index.html
```

👈🏼👀