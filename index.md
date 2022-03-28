---
layout: workshop      # NO CAMBIAR ESTO 
carpentry: "swc"    # qué tipo de Carpentry (ya sea "lc", "dc" o "swc")
venue: "FLISoL Loja 2022 - En línea"        # nombre breve del espacio donde se lleva adelante el taller, sin dirección (por ejemplo, "Universidad de Buenos Aires")
address: null      # dirección completa del espacio donde se realizará el taller (por ejemplo, "Aula 3, Av. Córdoba 1234, Buenos Aires, Argentina")
country: "Ecuador"      # código ISO del país, dos letras en minúscula como por ejemplo "fr" (ver https://en.wikipedia.org/wiki/ISO_3166-1)
language: "Español"     # código ISO del idioma, dos letras en minúscula como por ejemplo "fr" (ver https://en.wikipedia.org/wiki/ISO_639-1)
latlng: null       # latitud y longitud del espacio en formato decimal (por ejemplo, "41.7901128,-87.6007318" - usar http://www.latlong.net/)
humandate: "Abril 27, 2022"    # fechas del taller en formato legible (por ejemplo, "Feb 17-18, 2020")
humantime: "6:00 pm - 9:00 pm"    # hora del taller en formato legible (por ejemplo, "9:00 am - 4:30 pm")
startdate: 2022-04-27      # fecha de inicio del taller en formato YYYY-MM-DD (por ejemplo, 2015-01-01)
enddate: 2022-04-27        # fecha de finalización del taller en formato YYYY-MM-DD, por ejemplo 2015-01-02
instructor: ["Denisse Fierro Arcos", "Linda Cabrera Orellana"] # lista de nombres de las instructoras separados por comas y entre corchetes, como ["Hedy Lamarr", "Ada Lovelace", "Madame Curie"]
email: ["galapagos@rladies.org"]    # lista de direcciones de correo electrónico de contacto con la **host** ó **lead instructor**, separadas por comas y entre corchetes, como ["ada.lovelace@ejemplo.org", "carrie.fisher@ejemplo.org", "hedy.lamarr@example.org"]
collaborative_notes:             # optional: URL de las notas colaborativas del taller, por ejemplo un Etherpad o documento de Google Docs 
eventbrite:           # optional: clave alfanumérica de registro en Eventbrite, por ejemplo "1234567890AB" (si se está utilizando Eventbrite)
---

{% comment %} Ver en los comentarios que siguen las instrucciones sobre cómo editar secciones específicas de esta plantilla de taller {% endcomment %}

{% comment %}
  ENCABEZADO

  Edita los valores en el bloque de arriba para tu taller.
  Si el valor no es 'true', 'false', 'null', o un número, por favor usa
  comillas dobles alrededor del valor, salvo que se especifique de otro modo.
  Por último ejecuta 'make workshop-check' *antes* de comitear para asegurarte que los cambios estan bien.
{% endcomment %}

{% comment %}
  EVENTBRITE

  Este bloque incluye el widget para registro en Eventbrite, en caso de que 'eventbrite' haya sido especificado en el encabezado. Puedes borrarlo si no estás usando Eventbrite, o dejarlo, ya que no se mostrará si el campo 'eventbrite' en el encabezado no fue especificado. 
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">Información General</h2>

{% comment %}
  INTRODUCCIÓN 

  Edita el párrafo introductorio general debajo si quieres modificar la presentación.
  
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% endif %}

{% comment %}
  PÚBLICO

  Explica quién es tu público. (En particular, cuenta a los lectores si el taller esta abierto sólo a personas de una institución o grupo en particular).
  {% endcomment %}
{% if page.carpentry == "swc" %}
  <strong>Quién: </strong> Este taller está dirigido a cualquier persona con interés o necesidad de aplicar un sistema de control de versiones en su trabajo o estudio. No es necesario ningún conocimiento previo sobre Git, ya que los herramientas serán presentadas en el taller. Es recomendable, aunque no estrictamente necesario, que los participantes estén familiarizados con el uso de la Terminal.
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

{% comment %}
  UBICACIÓN

  Este bloque muestra la dirección y enlaces a mapas con instrucciones para llegar, si la latitud y longitud fueron definidas. Puedes utilizar http://itouchmap.com/latlong.html para encontrar la lat/long de una dirección. 
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Dónde:</strong>
  {{page.address}}.
  Obtener direcciones con:
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  o
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
  FECHA

  Este bloque muestra la fecha y enlaces a Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>Cuándo:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  REQUERIMIENTOS ESPECIALES
  
  Modifica este bloque si hay algún requerimiento especial.
{% endcomment %}
<p id="requirements">
  <strong>Requerimientos:</strong> Las asistentes deben traer una computadora portátil con sistema operativo Mac, Linux o Windows (no tablet, Chromebook, etc.), que tenga permisos de administradora habilitados. Deben tener algunos paquetes de software específicos instalados (listados <a href="#setup">aquí</a>). 
	
También es requerido que respeten el 
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Código de Conducta</a>. 
</p>


{% comment %}
  ACCESIBILIDAD

  Modifica este bloque si existen barreras de accesibilidad o instrucciones especiales.
{% endcomment %}
<p id="accessibility">
  <strong>Accesibilidad:</strong> Estamos comprometidas a hacer que este taller sea accesible para todas.
</p>
<p>
  Los materiales se compartirán antes del taller a las personas registradas. El taller será en línea por lo que es necesario que participantes tengan acceso a una conexión estable al internet y una computadora propia. Si podemos ayudar a facilitar el aprendizaje, por ejemplo, poniendo a participantes en una misma ciudad en contacto para que organicen sesiones en grupo, contáctanos utilizando los detalles de contacto listados abajo.
</p>

{% comment %}
  DIRECCIONES DE CORREO ELECTRÓNICO DE CONTACTO

  Muestra los correos electrónicos de contacto definidos en el archivo de configuración.
{% endcomment %}
<p id="contact">
  <strong>Contacto</strong>:
  Por favor escribe a
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        o
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    a ser anunciado
  {% endif %}
  para más información.
</p>

<hr/>

{% comment %}
  SCHEDULE



 Muestra el cronograma del taller. Edita los ítems y horarios en la tabla para ajustarlos a tu planificación. Puede que quieras modificar 'Día 1' y 'Día 2' para mostrar fechas concretas o días de la semana.

{% endcomment %}
<h2 id="schedule">Cronograma</h2>

{% comment %} NO EDITAR LOS ENLACES A LAS ENCUESTAS {% endcomment %}
<p><em>Encuestas</em></p>
{% if page.carpentry == "swc" %}
<p>Por favor, asegúrese de completar estas encuestas antes y después del taller.</p>
<p><a href="{{ site.swc_pre_survey }}{{ site.github.project_title }}">Encuesta pre-taller</a></p>
<p><a href="{{ site.swc_post_survey }}{{ site.github.project_title }}">Encuesta post-taller</a></p>

{% elsif page.carpentry == "dc" %}
  <p>Por favor, asegúrese de completar estas encuestas antes y después del taller.</p>
<p><a href="{{ site.dc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.dc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif page.carpentry == "lc" %}
<p>Pregúntele a su instructor acerca de los detalles de la encuesta antes y después del taller.</p>
{% endif %}


{% if page.carpentry == "swc" %}
  {% include sc/schedule.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/schedule.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/schedule.html %}
{% endif %}

{% comment %}
  Notas de colaboración

  Si quieres usar un Etherpad, ve a

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  donde 'YYYY-MM-DD-site' es el identificador de su taller,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
 Utilizaremos este <a href="{{page.collaborative_notes}}"> documento colaborativo </a> para chatear, tomar notas y compartir URL y fragmentos de código.
</p>
{% endif %}

<hr/>

{% comment %}
  CURRICULA

  En inglés, syllabus. Muestra que tópicos van a ser cubiertos.

  1. Si tu taller es sobre R antes que Python, remueve el comentario
     alrededor de esa sección y pon un comentario alrededor de la sección Python.
  2. Algunos talleres van a remover SQL.
  3. Por favor asegúrate que la lista de tópicos está sincronizada con lo que
     pretendes enseñar.
  4. Podría ser que necesites mover los campos div con class="col-md-6" alrededor
     dentro de los div con class="row" para balancear el diseño multi-columnar.

  Este es uno de los lugares donde la gente frecuentemente comete errores, así que
  por favor observa la previsualización del sitio antes de comitear, y asegúrate
  de ejecutar también 'tools/check'.
{% endcomment %}
<h2 id="syllabus">Currícula</h2>

{% if page.carpentry == "swc" %}
  {% include sc/syllabus.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/syllabus.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/syllabus.html %}
{% endif %}

<hr/>

{% comment %}
  CONFIGURACIÓN
 
  Borra las secciones irrelevantes de las instrucciones de configuración. Cada sección esta dentro de un 'div' que no contiene clases para que el comienzo y el final sean más fáciles de encontrar.
  Este es otro lugar en donde las personas cometen errores de forma más frecuente, por favor previsualiza tu sitio antes de commitear y además asegurate de ejecutar 'tools/check'.
  
{% endcomment %}

<h2 id="setup">Configuración</h2>

<p>
  Para participar en un taller de
  {% if page.carpentry == "swc" %}
  Software Carpentry
  {% elsif page.carpentry == "dc" %}
  Data Carpentry
  {% elsif page.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  ,
  necesitarás acceso a algunos de los programas descritos abajo.
  Además, necesitarás la versión más reciente de un navegador web como Google Chrome, Mozilla Firefox, o Safari.
</p>
<p>
  Puedes encontrar una lista de problemas comunes (en inglés) que ocurren durante la instalación como referencia que pueden ser útiles para encontrar una solución: 
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

<div id="shell"> {% comment %} Start of 'shell' section. {% endcomment %}
  <h3>La terminal Bash</h3>

  <p>
    Bash es una de las terminales más frecuentemente utilizadas, que te permite realizar tareas simples de forma rápida.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="shell-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=339AEqk9c-8">Video Tutorial</a>
      <ol>
        <li>Descarga el <a href="https://git-for-windows.github.io/">instalador</a> de Git para Windows.</li> 
        <li>Ejecuta el instalador y sigue los siguientes pasos:
          <ol>
            {% comment %} Instalación de Git 2.8.2 {% endcomment %}
            {% comment %} Información {% endcomment %}
            <li>Click en "Siguiente".</li>
            {% comment %} Seleccionar Componentes{% endcomment %}
            <li>Click en "Siguiente".</li>
            {% comment %} Ajustar tu variable de entorno PATH {% endcomment %}
            <li>
              <strong>
                Dejar seleccionado "Utilizar Git desde la Línea de Comando de Windows" y click en "Siguiente".
              </strong>
                Si olvidaste hacer esto, los programas que necesitas para el taller no funcionarán correctamente. 
		Si esto sucede vuelve a ejecutar el instalador y selecciona la opción adecuada.
            </li>
            {% comment %} Eligiendo el ejecutable SSH {% endcomment %}
            <li>Click en "Siguiente".</li>
            {% comment %} Configurando los finales de línea {% endcomment %}
            <li>
              <strong>
                Deja seleccionado "Deshabilitar estilo Windows, confirmar estilo Unix para los finales de líneas" y click en "Siguiente".
              </strong>
            </li>
            {% comment %} Configurando el emulador de la terminal para ser utilizado con Git Bash {% endcomment %}
            <li>
              <strong>
                Dejar seleccionado "Utilizar ventana de consola de Windows por defecto" y click en "Next".
              </strong>
            </li>
            {% comment %} Configurando ajustes de rendimiento experimental {% endcomment %}
            <li>Click en "Instalar".</li>
            {% comment %} Instalando {% endcomment %}
            {% comment %} Completando el Asistente de Instalación de Git{% endcomment %}
            <li>Click en "Finalizar".</li>
          </ol>
        </li>
        <li>
          Si tu variable de entorno "HOME" no está configurada (o si no sabes qué es esto):
          <ol>
            <li>Abre una terminal (Abrir Menú Inicio y escribir <code>cmd</code> y presionar [Enter])</li>
            <li>
              Estcribe la siguiente línea en la ventana de la terminal exactamente como sigue:
              <p><code>setx HOME "%USERPROFILE%"</code></p>
            </li>
            <li>Presiona [Enter], deberías ver <code>SUCCESS: Specified value was saved.</code></li>
            <li>Sal de la terminal escribiendo <code>exit</code> y presionando [Enter]</li>
          </ol>
        </li>
      </ol>
      <p>Esto instalará tanto Git y Bash en el programa Git Bash.</p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-macosx">macOS</h4>
      <p>
        La terminal por defecto en todas las versiones de macOS es Bash, así que no es necesario instalar nada. Puedes acceder a Bash desde la Terminal (se encuentra en
        <code>/Applications/Utilities</code>).
        Puedes ver el <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a> de instalación de Git a modo de ejemplo de cómo abrir la Terminal. 
	Puede que quieras mantener la Terminal en tu dock para este taller. 
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-linux">Linux</h4>
      <p>
        La consola por defecto es generalmente Bash, pero si tu máquina está configurada de forma distinta puedes ejecutarla abriendo una terminal y escribiendo <code>bash</code>. No hay necesidad de instalar nada.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'shell' section. {% endcomment %}
<div id="git"> {% comment %} Start of 'Git' section. La compatibilidad de GitHub  
           esta en https://help.github.com/articles/supported-browsers/{% endcomment %}
  <h3>Git</h3>

  <p>
    Git es un sistema de versión de control que permite hacer un seguimiento de
    quién hizo qué cambios, dónde y cuándo. Git tiene la opción de actualizar fácilmente
    una versión publica o compartida de tu código a través de plataformas como <a href="https://github.com/">github.com</a>.
    Vas a necesitar un navegador web
    <a href="https://help.github.com/articles/supported-browsers/">soportado</a>
    por GitHub (actualmente incluyen Chrome, Firefox, Safari, o Internet Explorer 9 o su versión más reciente).
  </p>
  <p>
    También necesitarás una cuenta en <a href="https://github.com/">github.com</a>
    para alguna partes de la lección de Git. Las cuentas básicas en GitHub son gratuitas.
    Te incentivamos a crear una cuenta en GitHub si todavia no tienes una.
    Por favor considera qué información persional te gustaría hacer pública.
    Puedes revisar este sitio web con 
    <a href="https://help.github.com/articles/keeping-your-email-address-private/">instrucciones
    sobre cómo mantener tu dirección de email privada</a>.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="git-windows">Windows</h4>
      <p>
        Git debería estar instalado en tu computadora como parte
        de tu instalacion de Bash (mira la sección anterior sobre cómo instalar Bash).
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">Video Tutorial</a>
      <p>
        <strong>Para OS X 10.9 y superiores</strong>, instala Git para Mac
        ejecutando el instalador más reciente de "Mavericks", puedes descargarlo
        <a href="http://sourceforge.net/projects/git-osx-installer/files/">desde aquí</a>.
        Después de instalar Git, no vas a ver nada en tu carpeta <code>/Applications</code> porque
        Git es un programa de línea de comando.
        <strong>Para versiones más antiguas de OS X (10.5-10.8)</strong>
        Usa el instalador <a href="http://sourceforge.net/projects/git-osx-installer/files/"> disponible </a>
        más reciente para "Snow-leopard".
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-linux">Linux</h4>
      <p>
        Si Git no está aún instalado en tu máquina, puedes tratar de instalarlo a través
        de los repositorios de tu distribución. Para Debian/Ubuntu ejecuta
        <code>sudo apt-get install git</code> y para Fedora
        <code>sudo dnf install git</code>
      </p>
    </div>
  </div>
</div> {% comment %} End of 'Git' section. {% endcomment %}

<div id="editor"> {% comment %} Start of 'editor' section. {% endcomment %}
  <h3>Editor de Texto</h3>

  <p>
	Cuando estés escribiendo código, es bueno tener un editor de texto que esté
    optimizado para escribir código, con características como predicción automática de
    código, uso de colores para resaltar palabras clave, etc. El editor de texto predeterminado en macOS y
    Linux es usualmente Vim, el cual no es famoso por ser
    intuitivo. Si accidentalmente te encuentras atascado en él, intenta
    escribiendo la clave de escape (ESC), seguido de <code>:q!</code> (es decir: dos puntos, la letra 'q' minúscula,
    y signo de exclamación), luego presionando Volver para regresar al intérprete de comandos.
</p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="editor-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=339AEqk9c-8">Video Tutorial</a>
      <p>
	Nano es un editor básico y el predeterminado que usan los instructores en el taller.
	Para instalarlo,
	descarga el<a href="{{site.swc_installer}}">
          {% if page.carpentry == "swc" %}
          Software Carpentry
          {% elsif page.carpentry == "dc" %}
          Data Carpentry
          {% elsif page.carpentry == "lc" %}
          Libreria Carpentry
          {% endif %}
          Instalador de Windows
	</a>
	 y haz doble click en el archivo para iniciar la instalación.
        <strong>Esta instalación requiere una conexión a Internet.</strong>
      </p>
      <p>
        Otros editores que puedes usar son
        <a href="http://notepad-plus-plus.org/">Notepad++</a> o
        <a href="http://www.sublimetext.com/">Sublime Text</a>.
        <strong>
	Ten en cuenta que debes
        agregar tu directorio de instalación a la ruta del sistema. </strong>
        Si tienes dificultades, pídele a tu instructor que te ayude a hacer esto.
	</p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-macosx">macOS</h4>
      <p>
	Nano es un editor básico y el predeterminado que usan los instructores en el taller.
        Mira este <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">vídeo tutorial</a>
       	sobre la instalación de Git y Nano.
	Recuerda que el edito de texto debe estar preinstalado en tu computador antes de iniciar el taller. 
	</p>
      <p>
	Otros editores que puedes usar son
        <a href="http://www.barebones.com/products/textwrangler/">Text Wrangler</a> o
        <a href="http://www.sublimetext.com/">Sublime Text</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-linux">Linux</h4>
      <p>
	Nano es un editor básico y el predeterminado que usan los instructores en el taller.
      </p>
      <p>
	Otros editores que puedes usar son
        <a href="https://wiki.gnome.org/Apps/Gedit">Gedit</a>,
        <a href="http://kate-editor.org/">Kate</a> or
        <a href="http://www.sublimetext.com/">Sublime Text</a>.
	Recuerda que el edito de texto debe estar preinstalado en tu computador antes de iniciar el taller. 
      </p>
    </div>
  </div>
</div> {% comment %} End of 'editor' section. {% endcomment %}

<div id="r"> {% comment %} Start of 'R' section. {% endcomment %}
  <h3>R</h3>

  <p>
    <a href="http://www.r-project.org">R</a> es un lenguaje de programación 
    especialmente poderoso para la exploración y visualización de datos, así como para  
    análisis estadísticos. Para trabajar con R usamos el programa 
    <a href="http://www.rstudio.com/">RStudio</a>.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="r-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=q0PjTAylwoU">Video Tutorial en inglés </a>
      <p>

        Después de descargar 
        <a href="http://cran.r-project.org/bin/windows/base/release.htm">este archivo .exe </a>
        desde <a href="http://cran.r-project.org/index.html">CRAN</a>, ábrelo e instala R.
        Además, instala el entorno de desarrollo integrado (IDE por sus siglas en inglés, Integrated Development Environment) 
        <a href="http://www.rstudio.com/ide/download/desktop">RStudio</a>.
        Ten en cuenta que si tienes cuentas separadas de usuario y administrador en tu computador,
	debes correr los instaladores como administrador (haz click derecho en el 
        archivo .exe y selecciona "Ejecutar como administrador" en lugar de hacer doble click).  
        De lo contrario pueden ocurrir problemas cuando instales paquetes en R.


      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=5-ly3kyxwEg">Video Tutorial en inglés</a>
      <p>
        Después de descargar 
        <a href="http://cran.r-project.org/bin/macosx/R-latest.pkg">este archivo .pkg </a>
        desde <a href="http://cran.r-project.org/index.html">CRAN</a>, ábrelo e instala R.
        Además, instala el entorno de desarrollo integrado (IDE por sus siglas en inglés, Integrated Development Environment) 
        <a href="http://www.rstudio.com/ide/download/desktop">RStudio</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-linux">Linux</h4>
      <p>
        Puedes descargar los archivos binarios para tu distribución
        desde <a href="http://cran.r-project.org/index.html">CRAN</a>. También
        puedes usar tu administrador de paquetes (por ejemplo: para Debian/Ubuntu
        corre <code>sudo apt-get install r-base</code> y para Fedora corre
        <code>sudo dnf install R</code>).  Además, por favor instala el entorno de desarrollo integrado 
	(IDE por sus siglas en inglés, Integrated Development Environment) 
        <a href="http://www.rstudio.com/ide/download/desktop">RStudio</a>.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'R' section. {% endcomment %}


{% comment %}
 
 
<div id="sql"> {% comment %} Start of 'SQLite' section. {% endcomment %}
  <h3>SQLite</h3>

  <p>
    SQL is a specialized programming language used with databases.  We
    use a simple database manager called
    <a href="http://www.sqlite.org/">SQLite</a> in our lessons.
  </p>

  <p>
    SQL es un lenguaje de programación usado en bases de datos.
    Nosotras en nuestras lecciones usamos
    <a href="http://www.sqlite.org/">SQLite</a>.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="sql-windows">Windows</h4>
      <p>
        The <a href="{{site.swc_installer}}">
          {% if page.carpentry == "swc" %}
          Software Carpentry
          {% elsif page.carpentry == "dc" %}
          Data Carpentry
          {% elsif page.carpentry == "lc" %}
          Library Carpentry
          {% endif %}
          Windows Installer
	</a>
        installs SQLite for Windows.
        If you used the installer to configure nano, you don't need to run it again.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="sql-macosx">macOS</h4>
      <p>
        SQLite comes pre-installed on macOS.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="sql-linux">Linux</h4>
      <p>
        SQLite comes pre-installed on Linux.
      </p>
    </div>
  </div>

  <p><strong>If you installed Anaconda, it also has a copy of SQLite
    <a href="https://github.com/ContinuumIO/anaconda-issues/issues/307">without support to <code>readline</code></a>.
    Instructors will provide a workaround for it if needed.</strong></p>
</div> {% comment %} End of 'SQLite' section. {% endcomment %}

<div id="openrefine"> {% comment %} Start of 'OpenRefine' section. {% endcomment %}
  <h3>OpenRefine</h3>
  <p>
    For this lesson you will need <em>OpenRefine</em> and a
    web browser. <em>Note:</em> this is a Java program that runs on your machine (not in the cloud).
    It runs inside a web browser, but no web connection is needed.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="openrefine-windows">Windows</h4>
      <p>
        Check that you have either the Firefox or the Chrome browser installed and set as your default browser.
        <strong>OpenRefine runs in your default browser.</strong>
        It will not run correctly in Internet Explorer.
      </p>
      <p>Download software from <a href="http://openrefine.org/">http://openrefine.org/</a></p>
      <p>Create a new directory called OpenRefine.</p>
      <p>Unzip the downloaded file into the OpenRefine directory by right-clicking and selecting "Extract ...". </p>
      <p>Go to your newly created OpenRefine directory.</p>
      <p>Launch OpenRefine by clicking <code>google-refine.exe</code> (this will launch a command prompt window, but you can ignore that - just wait for OpenRefine to open in the browser).</p>
      <p>If you are using a different browser, or if OpenRefine does not automatically open for you, point your browser at <a href="http://127.0.0.1:3333/">http://127.0.0.1:3333/</a> or <a href="http://localhost:3333">http://localhost:3333</a> to use the program.</p>
    </div>
    <div class="col-md-4">
      <h4 id="openrefine-mac">Mac</h4>
      <p>Check that you have either the Firefox or the Chrome browser installed and set as your default browser. <strong>OpenRefine runs in your default browser.</strong> It may not run correctly in Safari.</p>
      <p>Download software from <a href="http://openrefine.org/">http://openrefine.org/</a>.</p>
      <p>Create a new directory called OpenRefine.</p>
      <p>Unzip the downloaded file into the OpenRefine directory by double-clicking it.</p>
      <p>Go to your newly created OpenRefine directory.</p>
      <p>Launch OpenRefine by dragging the icon into the Applications folder.</p>
      <p>Use <code>Ctrl-click/Open ... </code> to launch it.</p>
      <p>If you are using a different browser, or if OpenRefine does not automatically open for you, point your browser at <a href="http://127.0.0.1:3333/">http://127.0.0.1:3333/</a> or <a href="http://localhost:3333">http://localhost:3333</a> to use the program.</p>
    </div>
    <div class="col-md-4">
      <h4 id="openrefine-linux">Linux</h4>
      <p>Check that you have either the Firefox or the Chrome browser installed and set as your default browser. <strong>OpenRefine runs in your default browser.</strong></p>
      <p>Download software from <a href="http://openrefine.org/">http://openrefine.org/</a>.</p>
      <p>Make a directory called OpenRefine.</p>
      <p>Unzip the downloaded file into the OpenRefine directory.</p>
      <p>Go to your newly created OpenRefine directory.</p>
      <p>Launch OpenRefine by entering <code>./refine</code> into the terminal within the OpenRefine directory.</p>
      <p>If you are using a different browser, or if OpenRefine does not automatically open for you, point your browser at <a href="http://127.0.0.1:3333/">http://127.0.0.1:3333/</a> or <a href="http://localhost:3333">http://localhost:3333</a> to use the program.</p>
    </div>
  </div>
</div> {% comment %} End of 'OpenRefine' section. {% endcomment %}


{% endcomment %}

{% comment %}
<div id="vm">
  <h3>Máquina Virtual</h3>

  <p>
      Algunos instructores prefieren que los alumnos utilicen una máquina virtual
      en lugar de instalar software en sus propias computadoras. Si tus
      instructores han elegido hacer esto, por favor: 
  </p>
  <ol>
    <li>
      Instalar <a href="https://www.virtualbox.org/">VirtualBox</a>.
    </li>
    <li>
      Descarga nuestra <a href="{{site.swc_vm}}">imagen de máquina virtual</a>.
      <strong>Advertencia:</strong> este archivo pesa 1.7 GByte, entonces por favor
      descárgalo <em>antes</em> de venir al taller.
    </li>
    <li>
      Carga la máquina virtual en VirtualBox seleccionando "Importar dispositivo" 
      y cargando el archivo <code>.ova</code> .
    </li>
  </ol>
</div>
{% endcomment %}
