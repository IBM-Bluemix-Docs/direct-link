---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-05-21"

keywords: faq, faqs, questions, answer, billing, fees, point-to-point, bandwidth, charges, redundancy, Global Routing, diversity, IPv6, BGP, charges, jumbo frames

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:faq: data-hd-content-type='faq'}

# Preguntas más frecuentes
{: #faqs}

Esta sección contiene respuestas a algunas preguntas frecuentes sobre {{site.data.keyword.cloud}} Direct Link. 

## ¿Cómo funciona IBM Cloud Direct Link?
{: #how-does-ibm-cloud-direct-link-work}
{:faq}

Para cada cliente de Direct Link, el equipo de IBM Cloud asigna una pequeña subred privada para construir una red punto a punto entre el direccionador de conexión (XCR) de {{site.data.keyword.BluSoftlayer_notm}} y el direccionador de extremo del cliente (CER). A continuación, {{site.data.keyword.BluSoftlayer_notm}} y el cliente configuran BGP para intercambiar rutas entre los entornos. Finalmente, {{site.data.keyword.BluSoftlayer_notm}} coloca el cliente en un VRF para permitir la implementación de rutas no exclusivas para el espacio de direcciones privado de la red remota del cliente.

## ¿Mide IBM Cloud el ancho de banda para los productos de Direct Link?
{: #does-ibm-cloud-meter-bandwidth-for-direct-link-products}
{:faq}

Sí. El uso de ancho de banda en el servicio de Direct Link entre clientes e IBM Cloud es gratuito y sin límite, IBM Cloud limita el ancho de banda de salida entre los servicios de IBM Cloud a Internet público.

## ¿Cuándo comienza la facturación con Direct Link?
{: #when-does-billing-begin-with-direct-link}
{:faq}

Las tarifas de Direct Link cubren el coste de la terminación del servicio en la infraestructura de IBM Cloud. 

Los servicios de la infraestructura se facturan por adelantado y comienzan tras la aceptación del pedido de nuestro cliente; sin embargo, debido a la naturaleza de IBM Cloud Direct Link, la facturación del servicio Direct Link empieza cuando se establece una sesión BGP (Border Gateway Protocol) con IBM Cloud, o bien 30 días después de que se proporcione la clave de servicio al cliente. 

La facturación se detiene después de que (1) un cliente solicite que se suprima un circuito Y (2) el proveedor de conexión o el proveedor de servicios de red desaprovisionen el circuito.

## ¿Qué cargos adicionales de otras partes tendré con Direct Link?
{: #what-additional-charges-will-i-incur-from-other-parties-with-direct-link}
{:faq}

Puede tener cargos adicionales del proveedor de intercambio o del proveedor de servicio de red. Consulte a sus proveedores para obtener información sobre sus precios.

## ¿Cómo puedo conseguir redundancia con IBM Cloud Direct Link?
{: #how-can-i-achieve-redundancy-with-ibm-cloud-direct-link}
{:faq}

Direct Link no proporciona un servicio inherentemente redundante. Direct Link puede proporcionar diversas conexiones, que permiten a los clientes crear redundancia a través de BGP. Puede conseguir diversidad con Direct Link conectándose a más de un proveedor de IBM Cloud Direct Link Dedicated o proveedor de Exchange para {{site.data.keyword.BluSoftlayer_notm}}. Como alternativa, con Exchange y Connect puede aprovechar diversas conexiones NNI con los proveedores de IBM Cloud Direct Link.

## ¿Cuál es la diferencia entre el direccionamiento "local" predeterminado y el complemento de direccionamiento global para Direct Link?
{: #what-is-the-difference-between-the-default-local-routing-and-the-global-routing-add-on-for-direct-link}
{:faq}

Con nuestra oferta Direct Link estándar, puede enviar tráfico entre los centros de datos en su región seleccionada. Si necesita acceso a otros centros de datos fuera de la región especificada, debe solicitar el complemento de direccionamiento global. Este modelo se basa en ACL (listas de control de acceso) que se ponen en marcha en el momento en el que solicite la conexión de Direct Link. 

## ¿Por qué existe un paquete de complementos de direccionamiento global para Direct Link?
{: #why-does-a-global-routing-add-on-package-exist-for-direct-link}
{:faq}

Hemos añadido el complemento de direccionamiento global para evitar que nuestros clientes incurran en costes de datos inesperados al atravesar fuera del mercado local de su centro de datos. Se mantienen costes más bajos para la mayoría de nuestros clientes y se ofrece a los clientes la posibilidad de tener una presencia global y de llegar a todas las regiones del mundo fácilmente. Normalmente, sin embargo, un cliente sólo requiere un paquete de ancho de banda local.

## Si estoy conectado a un Direct Link Dedicated, Direct Link Connect o Direct Link Exchange en una región como Dallas, ¿tendré acceso a otras regiones de EE. UU. mediante Direct Link?
{: #if-i-am-connected-to-a-direct-link-dedicated}
{:faq}

Sí, podrá tener acceso a áreas fuera de su mercado local si elige el complemento de direccionamiento global. Si no se selecciona esta opción, el tráfico de Direct Link se limitará al mercado local para el PoP o el centro de datos que haya seleccionado. Consulte el [documento sobre precios](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link) para obtener más información.

## ¿Puedo conectarme a cualquier región disponible desde una ubicación de Direct Link determinada?
{: #can-i-connect-to-any-available-region-from-a-given-direct-link-location}
{:faq}

Sí, siempre que solicite Direct Link con el complemento de direccionamiento global.

## ¿Puedo restringir las regiones a las que puede llegar mi Direct Link?
{: #can-i-restrict-the-regions-that-my-direct-link-can-reach}
{:faq}

No. IBM Cloud ofrece dos opciones: (1) un solo mercado local o (2) todas las regiones, con el complemento de direccionamiento global.

## ¿Qué pasa si he utilizado el proceso de pedido automatizado de Direct Link para Equinix Cloud Exchange y se me ha asignado una subred que se solapa con mi red interna?
{: #what-if-i-used-the-direct-link-automated-ordering-process}
{:faq}

A partir de marzo de 2018, la práctica recomendada es cancelar el pedido automatizado y enviar una incidencia nueva para rellenar el cuestionario de Direct Link. Debe indicar si prefiere otra subred en el rango 10.254.x.x o en el rango 172.32.x.x.

## ¿Cuál es la diferencia entre Direct Link Exchange y Direct Link Connect?
{: #what-is-the-difference-between-direct-link-exchange-and-direct-link-connect}
{:faq}

Estos dos servicios son similares, de coste relativamente bajo, tolerantes a la latencia y son puntos de entrada rápidos a los beneficios de IBM Cloud Direct Link. En resumen, Exchange utiliza proveedores de centros de datos y Connect utiliza transportistas Telco. A continuación, se muestran detalles adicionales:

Se recomienda utilizar **Direct Link Exchange** a los clientes que prefieren utilizar un intercambio dentro de un centro de datos. Con un servicio de Exchange, los clientes pueden habilitar rápidamente la conectividad multinube para su coubicación, ya que los circuitos subyacentes ya se suministran (el resto de los proveedores de nube ya deben tener una interconexión física en el recurso).

Direct Link Exchange puede permitir un entorno compartido multinube mediante un puerto de intercambio de nube único, creado por una conexión NNI (de red a red) en la capa 2 entre IBM Cloud y el proveedor de Cloud Exchange Service. Hay disponibles velocidades de puerto de hasta 5 Gb.

**Direct Link Connect** es para los clientes que prefieren utilizar una red existente entre su propio despliegue local e IBM Cloud. Con un servicio de Direct Link Connect, los clientes pueden utilizar redes Telco nuevas y existentes (como por ejemplo MPLS) para habilitar IBM Cloud rápidamente, optimizando circuitos subyacentes subministrados previamente.

Con Direct Link Connect, los clientes pueden conectarse a IBM Cloud a través del proveedor de Connect, a través de una conexión de red a red (NNI), con el soporte de asociados de IBM en instalaciones de todo el mundo. Hay disponibles velocidades de puerto de hasta 5 Gb.

## ¿Cómo se comparan los proveedores de Direct Link Connect y Direct Link Exchange?
{: #how-do-direct-link-connect-and-direct-link-exchange-providers-compare}
{:faq}

Los proveedores de Connect son Telcos que tienen un alcance de red más allá del centro de datos. Los proveedores de Exchange están limitados a sus centros de datos. Ambos pueden habilitar la experiencia multinube para los clientes. Los proveedores de Exchange suelen necesitar la coubicación en sus centros de datos, mientras que los proveedores de Connect pueden llegar al sitio local del cliente y a los centros de datos.

## ¿Puede IBM dar soporte a IPv6 a través de Direct Link?
{: #can-ibm-support-ipv6-over-direct-link}
{:faq}

No para la sesión BGP. Tenemos que asignar nuestro /30 desde IPv4, y necesitamos que el cliente devuelva lo mismo.

## ¿Puede IBM utilizar IPv6 en la red privada?
{: #can-ibm-do-ipv6-on-the-private-network}
{:faq}

No. IPv6 es solo público.

## ¿Hay algún requisito especial de Direct Link para Verizon SCI? ¿Prefijo / ASN / VLAN BGP / etc.?
{: #are-there-any-special-direct-link-requirements-for-verizon-sci}
{:faq}

Verizon SCI es uno de los diversos servicios basados en MPLS, de capa 3 (IP VPN). Requiere que IBM establezca BGP con Verizon en lugar de hacerlo directamente con el cliente. Luego Verizon establece BGP con el cliente y anuncia rutas en consecuencia. Hay otros proveedores de servicios basados en 3 capas que participan en el programa Direct Link Connect. Los clientes deben ser conscientes de lo que solicitan y de cómo se comportará su cuenta cuando se conecten a IBM Cloud.

## ¿Da Direct Link soporte a cualquier tipo de QoS?
{: #does-direct-link-support-any-type-of-qos}
{:faq}

No podemos dar soporte a ninguna garantía de QoS. QoS requiere una correlación MPLS entre cada uno de los proveedores de servicio e IBM Cloud. Los proveedores de servicios de nube generalmente no pueden dar soporte a QoS en este momento, porque debe alcanzar de extremo a extremo e implicar a cada dispositivo que haya entre ambos. No hay ningún método alternativo disponible mediante "tunelado (tunneling)" ni por ningún otro método.

## ¿Da Direct Link soporte a las tramas Jumbo?
{: #does-direct-link-support-jumbo-frames}
{:faq}

Las tramas Jumbo (hasta 9214 bytes) reciben soporte en la versión Dedicated y Dedicated Hosting. 
El soporte en Connect y Exchange es teóricamente posible, pero requiere que el proveedor de servicio trabaje con IBM y garantice que la conexión de extremo a extremo da soporte a las tramas Jumbo, incluida la interfaz de red a red (NNI) subyacente.
De forma predeterminada, Exchange y Connect se configuran con soporte de MTU de 1500 bytes.

## Con Direct Link Connect, ¿cómo garantiza un cliente la diversidad de direccionador a través del mismo operador (ejemplo: Verizon en DAL03)?
{: #with-diret-link-connect-how-does-a-customer-ensure-router-diversity-through-the-same-carrier}
{:faq}

Disponemos de diversos XCR que crean diversos enlaces NNI con el operador. El mantenimiento de la diversidad depende del operador.

## Para Direct Link Connect ¿debe el cliente solicitar 2 enlaces para obtener redundancia o Direct Link Connect es redundante de forma inherente?
{: #for-diret-link-connect-does-a-customer-need-to-order-2-links-for-redundancy}
{:faq}

Solicite 2 enlaces para obtener diversidad. No ofrecemos redundancia entre conmutadores o direccionadores. Los clientes crean redundancia con sus configuraciones de BGP en cada enlace directo.

## ¿Es sencillo actualizar el ancho de banda la conexión Direct Link, para que pase por ejemplo de 1 GB a 5 GB?
{: #how-easy-is-it-to-upgrade-the-bandwidth-of-my-direct-link-connection}
{:faq}

Generalmente, instalaremos velocidades de 1 G y por debajo en ópticas de 1 G. Para conseguir velocidades de entre 2 G y 10 G, instalamos ópticas de 10 G. Por lo tanto, la actualización de 1 G a 5 G requeriría la asignación o inserción de nuevas ópticas. Este suceso afectaría al servicio. Si anticipa ese tipo de crecimiento, podría solicitar la instalación de fibras ópticas de 10 G al principio del despliegue de Direct Link o podría solicitar inicialmente 2 G para disponer de ópticas de 10 G.

## ¿Es ECMP el método adecuado para conseguir conexiones Direct Link redundantes?  ¿Qué alternativas existen?
{: #is-ecmp-the-way-to-go-for-redundant-direct-link-connections}
{:faq}

Tenga en cuenta que ECMP no está pensado para conexiones redundantes, sino para equilibrar la carga sobre dos enlaces. Con ECMP, ambas conexiones deben terminar en el mismo direccionador de interconexión (XCR) de IBM Cloud, lo que lo convierte en un punto único de anomalía. (Es decir, ECMP solo se puede suministrar como dos sesiones en el mismo XCR de IBM Cloud.) 

ECMP es una característica de BGP. Si busca redundancia, obtenga dos conexiones de Direct Link, una para cada XCR. Si desea utilizar ECMP y tiene redundancia, necesitará dos conexiones de Direct Link en cada XCR, de modo que pueda tener 2 sesiones de ECMP al mismo tiempo.

Como alternativa, algunos de nuestros clientes han configurado dos enlaces en diferentes XCR en el mismo centro de datos, por ejemplo WDC02, y luego han realizado la migración tras error cuando lo han necesitado mediante configuraciones de BGP. Esta configuración es menos redundante (menos segura) que tener conexiones Direct Link en dos centros de datos distintos, como por ejemplo WDC02 y WDC05.

## ¿Hay un SLA en las conexiones XCR de Direct Link hasta la conexión BCR de la cuenta?
{: #is-there-an-sla-on-the-diret-link-xr-connections}
{:faq}

Actualmente no hay ningún SLA en Direct Link. Los clientes pueden conseguir 99,999% de forma efectiva con 2 o más Direct Links configurados correctamente para la migración tras error utilizando BGP, pero IBM no puede controlar esto ni proporcionar un SLA en el mismo.

## ¿Dónde puedo obtener ayuda para configurar Direct Link?
{: #where-can-i-get-help-setting-up-a-direct-link}
{:faq}

Para conectarse a Direct Link, consulte [Configurar {{site.data.keyword.cloud_notm}} Direct Link](/docs/infrastructure/direct-link?topic=direct-link-how-to-order-ibm-cloud-direct-link-dedicated). Si necesita más ayuda, puede solicitar soporte de ingeniería en la incidencia que se ha abierto para el nuevo servicio. Incluso si es un servicio de API con Equinix, abrir una incidencia permitirá que un ingeniero lo vea. O póngase en contacto con su representante de ventas de IBM.

## En Direct Link Exchange, ¿IBM establece una contraseña de BGP?
{: #on-direct-link-exchange-does-ibm-set-a-bgp-password}
{:faq}

No establecemos ninguna contraseña de BGP para Direct Link Exchange de forma predeterminada. Hay una opción para especificar el ASN de BGP y asignamos direcciones IP de BGP. Además, es posible configurar una contraseña de BGP por motivos de autenticación; se debe poner en conocimiento de los ingenieros.
