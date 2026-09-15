# Strata Observatory

*Español más abajo.*

If you found this page through the `User-Agent` in your logs —
`strata-observatory/1 (+https://github.com/strataobservatory; strata@luiscalvoruiz.es)`— this is who we are and how
to make us slow down or stop.

## What we do

Strata Observatory keeps a dated, daily record of which MCP (Model Context Protocol) servers
are listed in public directories, and seals each day so that anyone can later check it
existed on that date. It is a measurement archive.

## How we read, and how often

- **Once a day**, every morning at 07:00 Madrid time.
- **We read the public listings** of MCP directories and registries. We also look, once
  a day, at the own cards of the 34 servers we found on 2 September on their own domains
  (`/.well-known/mcp.json` and similar): one request each. We do not probe other domains.
- **Your `robots.txt` comes first.** We fetch it once per pass and per host, before
  anything else, and we honour `Disallow` and `Crawl-delay` for `strata-observatory` and
  for `*`. If your `robots.txt` cannot be read (anything other than a 404 or 410), we do
  not read that host that day.
- **At most one request per second per host**, or slower if your `Crawl-delay` asks for it.
- **We always identify ourselves** with the `User-Agent` above. We never hide it.

## How to make us slow down or stop

1. **Add a rule to your `robots.txt`.** It takes effect on the next daily pass, with
   nobody on our side having to act:

   ```
   User-agent: strata-observatory
   Disallow: /
   ```

   Or keep us but slow us down with `Crawl-delay: <seconds>`.
2. **Or write to us** at **strata@luiscalvoruiz.es**, or
   [open an issue in this repository](https://github.com/strataobservatory/strataobservatory/issues/new).
   Someone reads it; say which host and what you want.

## Who we are

Strata Observatory is an independent project.

**How we observe, in full:** the method, every closed version of it, at
https://github.com/strataobservatory/strata-metodo

---

## En español

Si ha llegado aquí por el `User-Agent` de sus registros
—`strata-observatory/1 (+https://github.com/strataobservatory; strata@luiscalvoruiz.es)`—, esto es quiénes somos y
cómo pedirnos que bajemos el ritmo o paremos.

**Qué hacemos.** Strata Observatory lleva un registro diario y fechado de qué servidores MCP
(Model Context Protocol) aparecen en los directorios públicos. Sella cada día para que
cualquiera pueda comprobar después que existía en esa fecha. Es un archivo de medida.

**Cómo y cada cuánto.**
- Una vez al día, cada mañana a las 07:00, hora de Madrid.
- Leemos los listados públicos de los directorios y registros MCP. Además miramos una vez
  al día las fichas propias de los 34 servidores que hallamos el 2 de septiembre en su
  propio dominio (`/.well-known/mcp.json` y parecidas): una petición cada una. No sondeamos
  otros dominios.
- Primero, su `robots.txt`. Lo leemos una vez por pasada y por servidor, antes que nada, y
  respetamos `Disallow` y `Crawl-delay` para `strata-observatory` y para `*`. Si no se
  puede leer (cualquier respuesta distinta de un 404 o un 410), ese día no leemos ese
  servidor.
- Como mucho una petición por segundo y servidor, o más despacio si su `Crawl-delay` lo
  pide.
- Nos identificamos siempre con el `User-Agent` de arriba. Nunca lo ocultamos.

**Cómo pedirnos que bajemos o paremos.**
1. Una regla en su `robots.txt` (`User-agent: strata-observatory` / `Disallow: /`).
   Vale desde la pasada siguiente y nadie de nuestro lado tiene que hacer nada.
2. O escríbanos a **strata@luiscalvoruiz.es**, o
   [abriendo una incidencia en este repositorio](https://github.com/strataobservatory/strataobservatory/issues/new),
   diciendo qué servidor y qué quiere. Alguien lo lee.

**Quiénes somos.** Strata Observatory es un proyecto independiente.

**Cómo observamos, entero:** el método, con todas sus versiones cerradas, en
https://github.com/strataobservatory/strata-metodo
