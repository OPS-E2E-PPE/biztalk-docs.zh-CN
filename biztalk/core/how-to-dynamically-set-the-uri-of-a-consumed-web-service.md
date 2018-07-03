---
title: 如何动态设置已使用的 Web 服务的 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95829a28-7898-4757-87cc-40fc99bf707e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a33f8d7c82130e3e0867d51a1575f40ac4442b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998518"
---
# <a name="how-to-dynamically-set-the-uri-of-a-consumed-web-service"></a>如何动态设置已使用的 Web Services 的 URI
为已使用的 Web Services 创建 Web 端口时，您可以选择动态端口绑定。 选择动态端口绑定时，必须在运行时设置已使用的 Web Services 的 URI。 选择的 URI 必须调用与创建 Web 端口类型所使用的 Web Services 具有相同 Web 代理的 Web Services。  
  
> [!NOTE]
>  本主题介绍如何通过编程方式在业务流程中设置动态 SOAP 发送端口属性。 但是，无论发送端口为静态还是动态，您都可以在业务流程或自定义管道组件中设置这些属性。 有关自定义管道组件的详细信息，请参阅[开发自定义管道组件](../core/developing-custom-pipeline-components.md)。  
  
 相较于非 Web 端口的动态端口绑定而言，Web 端口的动态端口绑定具有不同行为。 为非 Web 端口选择动态绑定时，不能使用 SOAP 适配器。  
  
 使用动态 Web 端口来使用 Web Services 时，发送端口属性设置为默认值。 其中某些值在内部设置和其他值默认设置中的值为**SOAP 适配器处理程序**属性页。 您可以在使用动态发送端口时在业务流程中覆盖这些值。 有关详细信息，请参阅[注意事项使用 Web Services 时](../core/considerations-when-consuming-web-services.md)。  
  
## <a name="dynamically-change-the-uri-of-a-consumed-web-service"></a>动态更改使用的 Web 服务的 URI  
  
1.  添加 Web 端口中所述[如何添加 Web 端口](../core/how-to-add-a-web-port.md)。 但是，而不是选择**立即指定**端口绑定，选择**动态**端口绑定，如下图中所示。  
  
     ![](../core/media/ebiz-prog-wsc-dynamic.gif "ebiz_prog_wsc_dynamic")  
  
2.  在已使用的 Web 服务调用业务流程，添加**表达式**形状之前的某个时刻**发送**已连接到 Web 端口的形状。  
  
3.  在中**表达式**形状中，添加如下表达式：  
  
    ```  
    myWebPort(Microsoft.XLANGs.BaseTypes.Address) = "http://orders/myCompany.asmx";  
    ```  
  
> [!NOTE]
>  您可以从不同位置（包括传入消息、SQL 数据库或业务线应用程序）检索在 BizTalk 表达式编辑器中使用的 URI。  
  
## <a name="dynamically-modify-send-port-properties"></a>动态修改发送端口属性  
  
1. 在中**构造消息**使用来构造 Web 消息，添加形状**消息赋值**形状如果尚未存在。  
  
2. 在中**消息赋值**形状中，添加如下表达式：  
  
   ```  
   myWebMessage(SOAP.UseSSO) = true;  
   ```  
  
   SOAP 发送端口的所有属性都使用 SOAP 命名空间。  
  
   下表列出了可在使用动态 Web 端口时设置的 SOAP 发送端口属性。  
  
|        属性名称         |  类型   |                                                                                                                                                                                                                                                                                                 Description                                                                                                                                                                                                                                                                                                  |
|------------------------------|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   **AuthenticationScheme**   | String  |                                                                                                                                                                                                                             用于调用 Web Services 的验证方法<br /><br /> 默认值： 匿名<br /><br /> 其他允许的值： 基本、 摘要式、 NTLM                                                                                                                                                                                                                              |
|         **用户名**         | String  |                                                                                                                                                                                                                                                         为访问目标 Web Services 而指定的用户名。<br /><br /> 默认值： 空                                                                                                                                                                                                                                                          |
|         **密码**         | String  |                                                                                                                                                                                                                                                          要用于服务器的身份验证的用户密码。<br /><br /> 默认值： 空                                                                                                                                                                                                                                                           |
|    **ClientCertificate**     | String  |                                                                                                                                                                                                                                                        客户端安全套接字层 (SSL) 证书的指纹。<br /><br /> 默认值： 空                                                                                                                                                                                                                                                         |
|          **UseSSO**          | Boolean |                                                                                                                                                                                                                                                       指示此 Web 端口是否将使用单一登录 (SSO)。<br /><br /> 默认值：False                                                                                                                                                                                                                                                        |
| **AffiliateApplicationName** | String  |                                                                                                                                                                                                                                  此 Web 端口将用于兑换客户端凭据票证的 SSO 应用程序的名称。<br /><br /> 默认值： 空                                                                                                                                                                                                                                   |
|    **UseHandlerSetting**     | Boolean |                                                                                                                                                                                      指示此 Web 端口是否将使用 SOAP 发送处理程序 HTTP 代理设置。 **注意：** 如果**UseProxy**设置上下文属性，然后**UseHandlerSetting**上下文属性将被忽略。 <br /><br /> 默认值：False                                                                                                                                                                                       |
|         **UseProxy**         | Boolean |                                                                                                                                                                                 指示此 Web 端口是否将使用代理服务器访问目标 Web Services。 **注意：** 如果**UseProxy**设置上下文属性，然后**UseHandlerSetting**上下文属性将被忽略。 <br /><br /> 默认值：False                                                                                                                                                                                  |
|       **ProxyAddress**       | String  |                                                                                                                                                                                                                                      用于 Web Services 调用的 HTTP 代理的地址。<br /><br /> 默认值： 从 SOAP 发送处理程序属性中检索到。                                                                                                                                                                                                                                      |
|        **ProxyPort**         | Integer |                                                                                                                                                                                                                                       用于 Web Services 调用的 HTTP 代理的端口。<br /><br /> 默认值： 从 SOAP 发送处理程序属性中检索到。                                                                                                                                                                                                                                        |
|      **ProxyUsername**       | String  |                                                                                                                                                                                                                                                 为 HTTP 代理使用的用户名。<br /><br /> 默认值： 从 SOAP 发送处理程序属性中检索到。                                                                                                                                                                                                                                                 |
|      **ProxyPassword**       | String  |                                                                                                                                                                                                                                                 为 HTTP 代理使用的密码。<br /><br /> 默认值： 从 SOAP 发送处理程序属性中检索到。                                                                                                                                                                                                                                                  |
| **ClientConnectionTimeout**  |  Int32  |                                                                                                                                                                                                                                           HTTP 客户端连接的超时值。<br /><br /> 默认值： 与默认 ASP.NET HTTP 连接超时值相同。                                                                                                                                                                                                                                            |
|         **类型名称**         | String  |                                                                                                                                                                                                                                                  指定包含要调用的 Web 方法的类的名称。<br /><br /> 默认值： 空                                                                                                                                                                                                                                                  |
|        **MethodName**        | String  | 指定要调用的类的方法。 **注意：** 若要配置**MethodName**属性为静态 SOAP 发送端口以编程方式，您需要设置**方法名称**to **[以后指定]** 中**Web 服务**选项卡**SOAP 传输属性**BizTalk Server 管理控制台中的对话框。 有关详细信息**SOAP 传输属性**对话框中，请参阅**SOAP 传输属性对话框，Web 服务**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 <br /><br /> 默认值： 空 |
|       **程序集名称**       | String  |                                                                                                                                                                                                                                                      标识要加载和执行的 .NET 类型和程序集。<br /><br /> 默认值： 空                                                                                                                                                                                                                                                       |
|      **UnknownHeaders**      | String  |                                                                                                                                                                                                                                                           指定未知 SOAP 标头的序列化列表。<br /><br /> 默认值： 空                                                                                                                                                                                                                                                            |
|       **UserDefined**        | String  |                                                                                                                                                                                                                                                                        定义用户定义的类。<br /><br /> 默认值： 空                                                                                                                                                                                                                                                                         |
|        **UseSoap12**         | Boolean |                                                                                                                                                                                                             指定此项可生成将支持 SOAP 1.2 协议的代理代码。 如果此属性为 False，则会生成符合 SOAP 1.1 的代理代码。<br /><br /> 默认值：False                                                                                                                                                                                                             |
  
> [!NOTE]
>  除**ClientConnectionTimeout**设置，这些值只能动态设置使用时**动态**端口绑定。 它们是只读的使用时**立即指定**端口绑定。 可以设置**ClientConnectionTimeout**设置，并同时**立即指定**并**动态**端口绑定。  
  
## <a name="see-also"></a>请参阅  
 [SOAP 标头与已使用的 Web 服务](../core/soap-headers-with-consumed-web-services.md)   
 [创建 Web 端口](../core/creating-web-ports.md)