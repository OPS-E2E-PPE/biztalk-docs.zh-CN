---
title: 导入 Bindings2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, requirements
- importing, bindings
- bindings, importing
ms.assetid: 9e10bc04-aba8-430a-b8fd-de9399d54f88
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fab3b7677336a2d10daf365d7bf58d3c90aa9f35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382531"
---
# <a name="importing-bindings"></a>导入绑定
在本部分中的主题介绍如何绑定导入到 BizTalk 组或应用程序。  

 在导入绑定，请记住以下重要事项：  

- **将覆盖现有绑定。** 如果您导入的绑定具有与现有绑定相同的名称，现有绑定将被覆盖。 此外，如果绑定文件包含参与方和别名，参与方和应用程序中已存在具有相同名称的别名的任何绑定将被覆盖。  

- **在组中的所有绑定必须都是唯一的。** 如果绑定具有相同的名称，一个要导入已存在的组中，导入操作将失败。  

- **必须重新配置密码。** 出于安全原因，在导出绑定文件时 BizTalk Server 将从文件删除绑定密码。 导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。 发送端口在 BizTalk Server 管理控制台的传输属性对话框中配置密码，或接收位置。 有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  

- **主机组中必须存在。** 在其中绑定将导入和主机的信任级别必须匹配在 BizTalk 组中必须存在对应的绑定中指定的主机的主机。 否则，导入操作将失败。  

- **绑定导入行为取决于绑定的源。** 绑定可能已从程序集、 应用程序或组导出。 具体取决于从绑定的导出，导入操作可能具有不同的效果下, 表中所示。  


  |        绑定源         |                                                                        导入到应用程序                                                                        |                                                                                                     导入到组                                                                                                      |
  |---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |  从程序集导出的绑定   | 指定应用程序中的必须包含与从中导出绑定文件的程序集同名的程序集。 否则，导入操作将失败。 |                        组必须包含程序集和具有相同名称的程序集和从中导出绑定文件的应用程序作为应用程序。 否则，导入将失败。                        |
  | 从应用程序导出的绑定 |            从中导出绑定文件的应用程序必须具有与指定的应用程序相同的名称。 否则，导入操作将失败。            |                从中导出绑定文件的应用程序必须在其中导入绑定在组中具有与应用程序相同的名称。 否则，导入操作将失败。                |
  |    从组导出的绑定     | 从中导出绑定文件的组必须包含具有指定的应用程序同名的应用程序。 否则，导入操作将失败。  | 绑定将导入对应的应用程序。 换而言之，从中导出绑定的组中的应用程序的绑定将导入到当前组中具有相同名称的应用程序。 |


- **适配器的 Name 属性可能不正确。** 如果绑定文件包括适配器的设置，请验证绑定文件中 TransportType 元素的 Name 属性是否为适配器在 BizTalk Server 管理控制台中配置相同 (在平台设置下 > 适配器)。  

   具体而言，应验证这种情况，导入中的绑定时[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]到 BizTalk Server。 某些传输方式，这可能是一个问题是，如下所示：  

  -   MQS  

  -   MSMQ  

  -   POP3  

  -   Windows SharePoint Services  

## <a name="in-this-section"></a>本节内容  

-   [如何将绑定导入 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)  

-   [如何将绑定导入 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)  

-   [如何导入 EDI-AS2 解决方案的绑定](../core/how-to-import-bindings-for-an-edi-as2-solution.md)