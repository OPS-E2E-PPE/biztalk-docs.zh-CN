---
title: 导入 Bindings2 |Microsoft 文档
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
ms.openlocfilehash: 2f2c92d5469f88494c77ad062d97c53768572a5b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006126"
---
# <a name="importing-bindings"></a>导入绑定
本部分中的主题介绍如何将绑定导入到 BizTalk 组或应用程序。  
  
 在导入的绑定，请记住以下重要事项：  
  
-   **将覆盖现有绑定。** 如果导入的绑定与现有的绑定同名，则现有的绑定将被覆盖。 此外，如果绑定文件包含参与方和别名，则应用程序中已存在的同名的参与方和别名的任何绑定将被覆盖。  
  
-   **在组中的所有绑定都必须都是唯一的。** 如果与您正在导入的绑定同名的绑定在组中已存在，导入操作将失败。  
  
-   **你必须重新配置密码。** 出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。 在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。 您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。 有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
-   **主机组中必须存在。** 要将绑定导入其中的 BizTalk 组中必须存在与绑定文件中指定的主机相对应的主机，并且，主机的信任级别必须匹配。 否则，导入操作将失败。  
  
-   **绑定导入行为取决于绑定的源。** 绑定可能已从程序集、应用程序或组中导出。 根据绑定的导出位置，导入操作可能具有不同的作用，如下表所示。  
  
    |绑定源|导入到应用程序|导入到组|  
    |----------------------------|-----------------------------------|----------------------------|  
    |从程序集导出的绑定|指定的应用程序必须包含与从中导出绑定文件的程序集同名的程序集。 否则，导入操作将失败。|组必须包含与从中导出绑定文件的程序集和应用程序同名的程序集和应用程序。 否则，导入操作将失败。|  
    |从应用程序导出的绑定|从中导出绑定文件的应用程序必须与指定的应用程序同名。 否则，导入操作将失败。|从中导出绑定文件的应用程序必须与要将绑定导入的组中的应用程序同名。 否则，导入操作将失败。|  
    |从组导出的绑定|从中导出绑定文件的组必须包含与指定的应用程序同名的应用程序。 否则，导入操作将失败。|绑定将导入对应的应用程序中。 换言之，从中导出绑定的组中的应用程序的绑定将导入到当前组中同名的应用程序内。|  
  
-   **适配器的名称属性可能不正确。** 如果绑定文件包括适配器的设置，请验证绑定文件中 TransportType 元素的 Name 属性与在 BizTalk Server 管理控制台中（在“平台设置”>“适配器”下）为该适配器配置的属性相同。  
  
     具体而言，你应验证这种情况，在导入来自绑定[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]给 BizTalk Server。 对于以下传输，这可能会是一个问题：  
  
    -   MQS  
  
    -   MSMQ  
  
    -   POP3  
  
    -   Windows SharePoint Services  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何将绑定导入到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)  
  
-   [如何将绑定导入 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)  
  
-   [如何导入绑定 EDI AS2 解决方案](../core/how-to-import-bindings-for-an-edi-as2-solution.md)