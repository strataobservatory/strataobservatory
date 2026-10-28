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
- **A redirect to another host is a new request.** Before following it we check our
  exclusion list and that host's `robots.txt`, and the per-host pace applies to it too. If
  any of them says no, we do not follow it.
- **`robots.txt` goes by scheme, host and port**, as its standard says: `http://` and
  `https://` on the same name each have their own, and we ask for it before following a
  redirect from one to the other.
- **We always identify ourselves** with the `User-Agent` above. We never hide it.

## How to make us slow down or stop

1. **Add a rule to your `robots.txt`.** It takes effect on the next daily pass, with
   nobody on our side having to act:

   ```
   User-agent: strata-observatory
   Disallow: /
   ```

   Or keep us but slow us down with `Crawl-delay: <seconds>`.

   We recognise our name however you write it: upper or lower case, with a hyphen,
   an underscore or a space, and with or without the `/1` version suffix.
   `Strata-Observatory`, `strata_observatory` and `strata-observatory/1` all stop us.
   A different name does not.
2. **If you cannot edit your `robots.txt`, write to us** at **strata@luiscalvoruiz.es**, or
   [open an issue in this repository](https://github.com/strataobservatory/strataobservatory/issues/new),
   saying which host or address. **We act on it within five days of receiving it**, and
   tell you when it is done.

**What we stop is the addresses you give us.** A card of yours published at another
address is another address, and to stop it you have to name it to us: we never link
objects by their owner, so we cannot know that a card in another directory is yours.

**What happens after.** The address gets no further request, not even for its
`robots.txt`. Its record closes with one last entry —an identifier, the day and "on
request", without the address or who asked— and from then on it is only counted. What was
recorded before stays as it was: no sealed day is rewritten.

**Coming back.** If you asked by email, our answer confirming that the address has been
stopped carries a one-time code. We keep only its fingerprint, never the code, and never
who asked: we keep only how the request reached us (email, issue or other). If you want us
to observe that address again, send us the code by email:
without it, leaving is permanent, because otherwise anyone could reopen someone else's address. **We never write
a code anywhere public.** If you asked through an issue, we stop the address just the same
and within the same five days, but without a code: that exit is permanent, and our answer
in the issue says so and why. If you may want to come back, ask by email. We do not send a
code to an email address later, because anyone could write quoting the issue before the
person who opened it; and asking again for an address already stopped does not give a new
code, for the same reason. On coming back the record keeps its identifier —nothing died, and nothing
is born again— and the days it was stopped stay outside every rate. If you stopped us with
your own `robots.txt`, you need no code: change it, and we read it again on the next pass.

**A directory can ask us to stop reading it, too.** We do, and the next version of the
method names it, because a directory is a public service and without its name nobody
could tell why the record changed.

## Who we are

Strata Observatory is an independent project, maintained by Luis Calvo Ruiz
([@luiscalvoruiz](https://github.com/luiscalvoruiz)). This GitHub account is the observatory's
automated account: what it publishes is done automatically by the observatory —the daily pass
and the publication of each version of the method—, and he answers for it and reads its issues.

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
- Una redirección a otro servidor es una petición nueva: antes de seguirla miramos nuestra
  lista de exclusión y el `robots.txt` de ese servidor, y también ahí va el ritmo por
  servidor. Si algo dice que no, no la seguimos.
- El `robots.txt` va por esquema, servidor y puerto, como dice su estándar: `http://` y
  `https://` con el mismo nombre tienen cada uno el suyo, y lo pedimos antes de seguir una
  redirección del uno al otro.
- Nos identificamos siempre con el `User-Agent` de arriba. Nunca lo ocultamos.

**Cómo pedirnos que bajemos o paremos.**
1. Una regla en su `robots.txt` (`User-agent: strata-observatory` / `Disallow: /`).
   Vale desde la pasada siguiente y nadie de nuestro lado tiene que hacer nada.

   Reconocemos nuestro nombre lo escriba como lo escriba: en mayúsculas o minúsculas,
   con guion, con guion bajo o con espacio, y con o sin el `/1` de versión.
   `Strata-Observatory`, `strata_observatory` y `strata-observatory/1` nos paran igual.
   Otro nombre distinto, no.
2. Si no puede tocar su `robots.txt`, escríbanos a **strata@luiscalvoruiz.es**, o
   [abra una incidencia en este repositorio](https://github.com/strataobservatory/strataobservatory/issues/new),
   diciendo qué servidor o dirección. **Lo cumplimos como mucho cinco días después de
   recibirlo**, y le avisamos cuando está hecho.

**Paramos las direcciones que nos dé.** Una ficha suya publicada en otra dirección es otra
dirección, y para pararla tiene que nombrárnosla: no enlazamos nunca los objetos por su
propietario, así que no podemos saber que una ficha en otro directorio es suya.

**Qué pasa después.** Esa dirección no recibe ninguna petición más, tampoco la de su
`robots.txt`. Su registro se cierra con una última entrada —un identificador, el día y «a
petición», sin la dirección ni quién lo pidió— y desde entonces sólo se cuenta. Lo
registrado antes se queda como estaba: ningún día sellado se reescribe.

**Volver.** Si nos lo pidió por correo, la contestación que le confirma que hemos parado la
dirección lleva un código de un solo uso. Guardamos sólo su huella, nunca el código, y nunca
quién lo pidió: sólo por dónde nos llegó la petición (correo, incidencia u otra vía). Si
quiere que volvamos a observar esa dirección, mándenos el código por correo:
sin él, la salida es permanente, porque si no cualquiera podría reabrir la dirección de otro. **Nunca
escribimos un código en un sitio público.** Si lo pidió con una incidencia, paramos la
dirección igual y en los mismos cinco días, pero sin código: esa salida es permanente, y la
contestación en la incidencia lo dice y dice por qué. Si quiere poder volver, pídalo por
correo. No mandamos el código a un correo después, porque cualquiera podría escribir citando
la incidencia antes que quien la abrió; y pedir otra vez la salida de una dirección ya
parada no da un código nuevo, por lo mismo. Al volver, el registro conserva su identificador —nada murió, y nada
nace otra vez— y los días que estuvo parado quedan fuera de toda tasa. Si nos paró con su
propio `robots.txt`, no necesita código: cámbielo, y lo volvemos a leer en la pasada
siguiente.

**Un directorio también puede pedirnos que dejemos de leerlo.** Lo hacemos, y la versión
siguiente del método lo nombra: un directorio es un servicio público, y sin su nombre nadie
podría saber por qué cambió el registro.

**Quiénes somos.** Strata Observatory es un proyecto independiente, mantenido por Luis Calvo
Ruiz ([@luiscalvoruiz](https://github.com/luiscalvoruiz)). Esta cuenta de GitHub es la cuenta
automática del observatorio: lo que publica lo hace el observatorio de forma automática —la pasada
diaria y la publicación de cada versión del método—, y él responde de ella y lee sus incidencias.

**Cómo observamos, entero:** el método, con todas sus versiones cerradas, en
https://github.com/strataobservatory/strata-metodo
