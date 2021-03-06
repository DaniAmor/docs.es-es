---
title: "Cómo crear un proveedor de tokens de seguridad personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 37e7f9541457c475bfe187485520df63a84f7555
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-custom-security-token-provider"></a>Cómo crear un proveedor de tokens de seguridad personalizado
En este tema se muestra cómo crear nuevos tipos de token con un proveedor de tokens de seguridad personalizado y cómo integrar el proveedor con un administrador de tokens de seguridad personalizado.  
  
> [!NOTE]
>  Cree un proveedor de tokens personalizado si los tokens proporcionados por el sistema ubicados en el espacio de nombres <xref:System.IdentityModel.Tokens> no coinciden con sus requisitos.  
  
 El proveedor de tokens de seguridad crea una representación de token de seguridad basada en información en el cliente o en las credenciales de servicio. Para usar el proveedor de tokens de seguridad personalizado en la seguridad [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], debe crear credenciales personalizadas e implementaciones de administrador de tokens de seguridad.  
  
 Para obtener más información acerca de las credenciales personalizadas y Administrador de tokens de seguridad, consulte el [Tutorial: creación de cliente personalizada y las credenciales de servicio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
 Para obtener más información acerca de las credenciales, vea clases token de administrador, el proveedor y el autenticador de seguridad, el [arquitectura de seguridad](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f).  
  
### <a name="to-create-a-custom-security-token-provider"></a>Para crear un proveedor de tokens de seguridad personalizado  
  
1.  Defina una clase nueva derivada de la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider>.  
  
2.  Implemente el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>. El método es responsable de crear y devolver una instancia del token de seguridad. El ejemplo siguiente crea una clase denominada `MySecurityTokenProvider`e invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> para devolver una instancia de la clase <xref:System.IdentityModel.Tokens.X509SecurityToken>. El constructor de clase necesita una instancia de la clase <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a>Para integrar un proveedor de tokens de seguridad personalizado con un administrador de tokens de seguridad personalizado  
  
1.  Defina una clase nueva derivada de la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>. (El siguiente ejemplo se deriva de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, que se deriva de la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>).  
  
2.  Si no está ya invalidado, invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>.  
  
     El método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> es responsable de devolver una instancia de la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider> adecuada al parámetro <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> que el marco de seguridad [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pasó al método. Modifique el método para devolver la implementación de proveedor de tokens de seguridad personalizado (creada en el procedimiento anterior) cuando se llama al método con un parámetro de token de seguridad adecuado. Para obtener más información sobre el Administrador de tokens de seguridad, consulte el [Tutorial: creación personalizada credenciales de cliente y servicio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
3.  Agregue la lógica personalizada al método para permitirle que devuelva su proveedor de tokens de seguridad personalizado basado en el parámetro <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>. El ejemplo siguiente devuelve el proveedor de tokens de seguridad personalizado si se cumplen los requisitos del token. Los requisitos incluyen un token de seguridad X.509 y la dirección del mensaje (que el token se utiliza para la salida del mensaje). Para todos los casos restantes, el código llama a la clase base para mantener el comportamiento proporcionado por el sistema para otros requisitos de token de seguridad.  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a>Ejemplo  
 A continuación se presenta una implementación <xref:System.IdentityModel.Selectors.SecurityTokenProvider> completa junto con una implementación <xref:System.IdentityModel.Selectors.SecurityTokenManager> correspondiente.  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.X509SecurityToken>  
 [Tutorial: Creación de credenciales de cliente y servicio personalizadas](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [Creación de un autenticador de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [Arquitectura de seguridad](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
