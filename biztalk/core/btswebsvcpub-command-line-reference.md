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
ms.openlocfilehash: c5d4098478bdb6257bdcfb2ed10b925a26c59d84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357802"
---
# <a name="btswebsvcpub-command-line-reference"></a>BTSWebSvcPub 命令行参考
本主题提供有关包含的 BTSWebSvcPub 命令行工具的参考信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 您可以使用 BTSWebSvcPub 创建 Web 服务 (.asmx) 用于发布业务流程通过 Web 服务，如下所示：  
  
## <a name="usage"></a>用法  
 **BTSWebSvcPub PathName [-Location:** *value* **] [-Overwrite] [-Anonymous]**  
  
 **[-Name:** *value* **] [-Namespace:** *value* **] [-TargetNamespace:** *value* **]**  
  
 **[-UnknownHeaders[** *+* **&#124;** *-* **]] [-SingleSignOn[** *+* **&#124;** *-* **]] [-ParameterStyle:** *value* **]**  
  
 **[-ConformanceClaims:** *value* **] [-ForceRequestResponse:** *value* **] [-ReceiveLocation]**  
  
 **[-ApplicationName:** *value* **]**  
  
## <a name="parameters"></a>Parameters  
  
|         参数         | Required |                                                           Description                                                            |
|---------------------------|----------|----------------------------------------------------------------------------------------------------------------------------------|
|       **PathName**        |   是    |                    BizTalk 程序集的路径和文件名称 (\*.dll) 或 web 服务说明 (\*.xml) 文件。                     |
|       **-Location**       |    否    |                                 要在其中发布位置。 (语法:"http://host[: 端口] / 路径")                                 |
|      **-Overwrite**       |    否    |                                                  覆盖指定的位置。                                                   |
|      **-Anonymous**       |    否    |                                              允许匿名访问 Web 服务。                                              |
|         **-Name**         |    否    |                    解决方案和程序集 （.sln 和.dll 文件） 将包含 Web 服务的名称。                    |
|      **-Namespace**       |    否    |                                             Web 服务代码的默认命名空间。                                              |
|   **-Targetnamespace**    |    否    |                        Web 服务的目标命名空间。 (示例:<http://www.northwindtraders.com>)                        |
|    **-UnknownHeaders**    |    否    |                                                  支持未知的 SOAP 标头。                                                   |
|    **-SinglesSignon**     |    否    |                                  支持 SharePoint Portal Server 单一登录 SOAP 标头。                                   |
|    **-ParameterStyle**    |    否    |                               消息的 SoapParameterStyle:"Default"、"Bare"或者"包装"。                               |
|  **-ConfirmanceClaims**   |    否    |                              Web 服务互操作性 (WSI) 声明："None"或"BasicProfile1_1"。                              |
| **-ForceRequestResponse** |    否    |                                将单向 BizTalk 操作公开为请求-响应 web 方法。                                |
|   **-ReceiveLocation**    |    否    |                                  创建指定的 BizTalk 应用程序中的接收位置。                                  |
|   **-ApplicationName**    |    否    | 要在其中创建 BizTalk 应用程序的名称的接收位置。 如果未指定，则使用默认 BizTalk 应用程序。 |
  
## <a name="sample"></a>示例  
 BTSWebSvcPub.exe "MyAssembly.dll" -Location:<http://localhost/MyVdir>  
  
 -Overwrite  
  
## <a name="remarks"></a>备注  
 参数名称不区分大小写，并且可以缩写。 参数值都区分大小写。  
  
## <a name="see-also"></a>请参阅  
 [如何使用 BizTalk Web Services 发布向导业务流程发布为 Web 服务](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)