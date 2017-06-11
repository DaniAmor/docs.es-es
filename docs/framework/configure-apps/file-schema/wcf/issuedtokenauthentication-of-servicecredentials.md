---
title: "&lt;issuedTokenAuthentication&gt; de &lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;issuedTokenAuthentication&gt; de &lt;serviceCredentials&gt;
Especifica un token personalizado emitido como una credencial de servicio.  
  
## Sintaxis  
  
```  
  
<issuedTokenAuthentication   
   allowUntrustedRsaIssuers="Boolean"  
   audienceUriMode="Always/BearerKeyOnly/Never"  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   samlSerializer="String"  
    trustedStoreLocation="CurrentUser/LocalMachine">  
      <allowedAudienceUris>  
      <add allowedAudienceUri="String"/>  
      </allowedAudienceUris>  
      <knownCertificates>   
         <add findValue="String"  
                 storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
      </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`allowedAudienceUris`|Obtiene el conjunto de los URI de destino para los que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.  Para obtener más información sobre cómo usar este atributo, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.|  
|`allowUntrustedRsaIssuers`|Un valor booleano que especifica si se permiten emisores de certificados de RSA que no son de confianza.<br /><br /> Las entidades emisoras de certificados \(CA\) firman los certificados para comprobar la autenticidad.  Un emisor que no es de confianza es una CA de la cual no se especifica que sea de confianza para firmar certificados.|  
|`audienceUriMode`|Obtiene un valor que especifica si se debería validar <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> del token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken>.  Este valor es del tipo <xref:System.IdentityModel.Selectors.AudienceUriMode>.  Para obtener más información sobre cómo usar este atributo, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.|  
|`certificateValidationMode`|Especifica el modo de validación del certificado.  Uno de los valores válidos de <xref:System.ServiceModel.Security.X509CertificateValidationMode>.  Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.  De manera predeterminada, es `ChainTrust`.|  
|`customCertificateValidatorType`|Cadena opcional.  Tipo y ensamblado utilizados para validar un tipo personalizado.  Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.|  
|`revocationMode`|Establece el modo de revocación que especifica si se produce una comprobación de revocación, y si se realiza en línea o sin conexión.  Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.|  
|`samlSerializer`|Un atributo de cadena opcional que especifica el tipo de SamlSerializer que se usa para la credencial del servicio.  El valor predeterminado es una cadena vacía.|  
|`trustedStoreLocation`|Enumeración opcional.  Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`knownCertificates`|Especifica una colección de elementos <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> que indican emisores de confianza para la credencial del servicio.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
  
## Comentarios  
 El escenario del token emitido tiene tres etapas.  En la primera etapa, un cliente que intenta obtener acceso a un servicio se remite a un *servicio de token seguro*.  El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad \(SAML\).  El cliente vuelve a continuación al servicio con el token.  El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.  Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.  
  
 Este elemento es el repositorio para todos los certificados de servicio de token seguro.  Para agregar certificados, utilice [\<knownCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).  Inserte un [\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) para cada certificado, tal y como se muestra en el ejemplo siguiente.  
  
```  
<issuedTokenAuthorization>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.  Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.  
  
 Para obtener más información sobre cómo utilizar este elemento de configuración, vea [Cómo: Configurar las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
## Vea también  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>   
 <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>   
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Cómo: Configurar las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)