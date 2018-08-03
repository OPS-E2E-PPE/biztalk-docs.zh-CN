---
title: BTSWebSvcPub 命令行参考 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e19dd4d-9f2c-4a17-9437-8701e1c274fb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62df9b42a9bc709275c836ed2d670d017b217ef6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980438"
---
# <a name="btswebsvcpub-command-line-reference"></a>BTSWebSvcPub 命令行参考
本主题提供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中包含的 BTSWebSvcPub 命令行工具的参考信息。 您可以使用 BTSWebSvcPub 创建 Web Services (.asmx)，以通过 Web Services 发布业务流程，BTSWebSvcPub 的具体用法如下：  
  
## <a name="usage"></a>用法  
 **BTSWebSvcPub 路径名 [-位置：** *值* **] [-覆盖] [-匿名]**  
  
 **[-名称：** *值* **] [-Namespace:** *值* **] [-TargetNamespace:** *值* **]**  
  
 **[-UnknownHeaders [** *+* **&#124;** *-* **]] [-单一登录 [** *+*  **&#124;** *-* **]] [-ParameterStyle:** *值***]**  
  
 **[-ConformanceClaims:** *值* **] [-ForceRequestResponse:** *值* **] [-接收位置]**  
  
 **[-应用程序名称：** *值* **]**  
  
## <a name="parameters"></a>Parameters  
  
|         参数         | Required |                                                           Description                                                            |
|---------------------------|----------|----------------------------------------------------------------------------------------------------------------------------------|
|       **PathName**        |   是    |                    BizTalk 程序集的路径和文件名称 (\*.dll) 或 web 服务说明 (\*.xml) 文件。                     |
|       **-位置**       |    “否”    |                                 要发布到的目标位置。 (语法:"http://host[: 端口] / 路径")                                 |
|      **-覆盖**       |    “否”    |                                                  覆盖指定的位置。                                                   |
|      **匿名**       |    “否”    |                                              允许匿名访问 Web Services。                                              |
|         **-名称**         |    “否”    |                    将要包含该 Web Services 的解决方案和程序集（.sln 文件和 .dll 文件）的名称。                    |
|      **-Namespace**       |    “否”    |                                             Web Services 代码的默认命名空间。                                              |
|   **-Targetnamespace**    |    “否”    |                        Web Services 的目标命名空间。 (示例:<http://www.northwindtraders.com>)                        |
|    **-UnknownHeaders**    |    “否”    |                                                  支持未知的 SOAP 标头。                                                   |
|    **-SinglesSignon**     |    “否”    |                                  支持 SharePoint Portal Server 单一登录 SOAP 标头。                                   |
|    **-ParameterStyle**    |    “否”    |                               消息的 SoapParameterStyle:"Default"、"Bare"或"Wrapped"。                               |
|  **-ConfirmanceClaims**   |    “否”    |                              Web 服务互操作性 (WSI) 声明:"None"或"BasicProfile1_1"。                              |
| **-ForceRequestResponse** |    “否”    |                                将单向 BizTalk 操作做为请求-响应 Web 方法公开。                                |
|   **-接收位置**    |    “否”    |                                  在指定 BizTalk 应用程序中创建接收位置。                                  |
|   **-应用程序名称**    |    “否”    | 要在其中创建接收位置的 BizTalk 应用程序的名称。 如果未指定，则使用默认 BizTalk 应用程序。 |
  
## <a name="sample"></a>示例  
 BTSWebSvcPub.exe "MyAssembly.dll" -Location:<http://localhost/MyVdir>  
  
 -Overwrite  
  
## <a name="remarks"></a>Remarks  
 参数名称不区分大小写，并且可以为缩写形式。 参数值是区分大小写的。  
  
## <a name="see-also"></a>请参阅  
 [如何使用 BizTalk Web Services 发布向导业务流程发布为 Web 服务](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)