# reportar-en-linea-simulacion-client-java

Carga de cuentas de personas físicas

## Requisitos

1. Java >= 1.7
2. Maven >= 3.3

## Instalación

Para la instalación de las dependencias se deberá ejecutar el siguiente comando:

```shell
mvn install -Dmaven.test.skip=true
```

> **NOTA:** Este fragmento del comando *-Dmaven.test.skip=true* evitará que se lance la prueba unitaria.


## Guía de inicio

### Paso 1. Agregar el producto a la aplicación

Al iniciar sesión seguir los siguientes pasos:

 1. Dar clic en la sección "**Mis aplicaciones**".
 2. Seleccionar la aplicación.
 3. Ir a la pestaña de "**Editar '@tuApp**' ".
    <p align="center">
      <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/edit_applications.jpg" width="900">
    </p>
 4. Al abrirse la ventana emergente, seleccionar el producto.
 5. Dar clic en el botón "**Guardar App**":
    <p align="center">
      <img src="https://github.com/APIHub-CdC/imagenes-cdc/blob/master/selected_product.jpg" width="400">
    </p>

### Paso 2. Capturar los datos de la petición

Los siguientes datos a modificar se encuentran en ***src/test/java/io/ReportarEnLineaSimulacion/client/api/CargaDeCuentasDePersonasFsicasApiTest.java***

Es importante contar con el setUp() que se encargará de inicializar la url. Modificar la URL ***('the_url')***, como se muestra en el siguiente fragmento de código:

```java
private final CargaDeCuentasDePersonasFsicasApi api = new CargaDeCuentasDePersonasFsicasApi();
private ApiClient apiClient = null;

@Before()
public void setUp() {
	this.apiClient = api.getApiClient();
	this.apiClient.setBasePath("the_url");
}
```

En el archivo **CargaDeCuentasDePersonasFsicasApiTest**, que se encuentra en ***test/java/io/ReportarEnLineaSimulacion/client/api*** se deberá modificar el siguiente fragmento de código con los datos correspondientes:

```java
@Test
public void registrarTest() throws ApiException {

	String xApiKey = "xxxxx";

	CargasPFRegistrarRequest request = new CargasPFRegistrarRequest();

	Encabezado encabezado = new Encabezado();
	encabezado.setClaveOtorgante("100000");
	encabezado.setNombreOtorgante("OTORGANTE");

	Persona persona = new Persona();

	Nombre nombre = new Nombre();
	nombre.setApellidoPaterno("PATERNO");
	nombre.setApellidoMaterno("MATERNO");
	nombre.setApellidoAdicional("null");
	nombre.setNombres("NOMBRE");
	nombre.setFechaNacimiento("19860627");
	nombre.setRfc("PAPN860627");
	nombre.setCurp("PAPN860627MOCNSB02");
	nombre.setNumeroSeguridadSocial("null");
	nombre.setNacionalidad("MX");
	nombre.setResidencia("1");
	nombre.setNumeroLicenciaConducir("null");
	nombre.setEstadoCivil("S");
	nombre.setSexo("F");
	nombre.setClaveElectorIFE("null");
	nombre.setNumeroDependientes("0");
	nombre.setFechaDefuncion("null");
	nombre.setTipoPersona("PF");
	nombre.setIndicadorDefuncion("1");

	Domicilio domicilio = new Domicilio();
	domicilio.setDireccion("CONOCIDA S/N");
	domicilio.setColoniaPoblacion("CONOCIDA");
	domicilio.setDelegacionMunicipio("ECATEPEC");
	domicilio.setCiudad("ECATEPEC");
	domicilio.setEstado("MEX");
	domicilio.setEstadoExtranjero("null");
	domicilio.setCp("55010");
	domicilio.setFechaResidencia("null");
	domicilio.setNumeroCelular("null");
	domicilio.setNumeroTelefono("null");
	domicilio.setExtension("null");
	domicilio.setFax("null");
	domicilio.setTipoDomicilio("C");
	domicilio.setTipoAsentamiento("2");
	domicilio.setOrigenDomicilio("2");

	Empleo empleo = new Empleo();
	empleo.setNombreEmpresa("VTA DE TORTILLAS");
	empleo.setDireccion("CONOCIDA S/N");
	empleo.setColoniaPoblacion("CONOCIDA");
	empleo.setDelegacionMunicipio("ECATEPEC");
	empleo.setCiudad("ECATEPEC");
	empleo.setEstado("MX");
	empleo.setCp("55010");
	empleo.setNumeroTelefono("null");
	empleo.setExtension("null");
	empleo.setFax("null");
	empleo.setPuesto("null");
	empleo.setFechaContratacion("null");
	empleo.setClaveMoneda("MX");
	empleo.setSalarioMensual("5600");
	empleo.setFechaUltimoDiaEmpleo("20180228");
	empleo.setFechaVerificacionEmpleo("null");
	empleo.setOrigenRazonSocialDomicilio("2");

	Cuenta cuenta = new Cuenta();
	cuenta.setClaveActualOtorgante("0000080008");
	cuenta.setNombreOtorgante("CIRCULO DE CREDITO");
	cuenta.setCuentaActual("TCDC000000");
	cuenta.setTipoResponsabilidad("O");
	cuenta.setTipoCuenta("F");
	cuenta.setTipoContrato("BC");
	cuenta.setClaveUnidadMonetaria("MX");
	cuenta.setValorActivoValuacion("null");
	cuenta.setNumeroPagos("17");
	cuenta.setFrecuenciaPagos("S");
	cuenta.setMontoPagar("0");
	cuenta.setFechaAperturaCuenta("20151103");
	cuenta.setFechaUltimoPago("20151201");
	cuenta.setFechaUltimaCompra("20151103");
	cuenta.setFechaCierreCuenta("20160101");
	cuenta.setFechaCorte("20180228");
	cuenta.setGarantia("null");
	cuenta.setCreditoMaximo("10000");
	cuenta.setSaldoActual("0");
	cuenta.setLimiteCredito("0");
	cuenta.setSaldoVencido("0");
	cuenta.setNumeroPagosVencidos("2");
	cuenta.setPagoActual(" V");
	cuenta.setHistoricoPagos("null");
	cuenta.setClavePrevencion("1");
	cuenta.setTotalPagosReportados("0");
	cuenta.setClaveAnteriorOtorgante("null");
	cuenta.setNombreAnteriorOtorgante("null");
	cuenta.setNumeroCuentaAnterior("null");
	cuenta.setFechaPrimerIncumplimiento("");
	cuenta.setSaldoInsoluto("null");
	cuenta.setMontoUltimoPago("null");
	cuenta.setFechaIngresoCarteraVencida("null");
	cuenta.setMontoCorrespondienteIntereses("2");
	cuenta.setFormaPagoActualIntereses("2");
	cuenta.setDiasVencimiento("3");
	cuenta.setPlazoMeses("null");
	cuenta.setMontoCreditoOriginacion("null");
	cuenta.setCorreoElectronicoConsumidor("null");
	cuenta.setEstatusCAN("01");
	cuenta.setOrdenPrelacionOrigen("01");
	cuenta.setOrdenPrelacionActual("01");
	cuenta.setFechaAperturaCAN("20151001");
	cuenta.setFechaCancelacionCAN("null");

	persona.setNombre(nombre);
	persona.setDomicilio(domicilio);
	persona.setEmpleo(empleo);
	persona.setCuenta(cuenta);

	request.setEncabezado(encabezado);
	request.setPersona(persona);
	
	try {
		T response = (T) api.registrarGenerico(xApiKey, request);
		Assert.assertTrue(response != null);
		logger.info(response.toString());
	} catch (ApiException e) {
		logger.error("ApiException: " ,e);
	}
}
```

### Paso 3. Ejecutar la prueba unitaria

Teniendo los pasos anteriores ya solo falta ejecutar la prueba unitaria, con el siguiente comando:

```shell
mvn test -Dmaven.install.skip=true
```
