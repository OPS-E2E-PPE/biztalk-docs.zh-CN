---
title: 如何配置 WCF CustomIsolated 接收处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e90add2-1a5e-4509-a98c-b3c297b4213f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00e52daaaefc3f85537dc3c51f8700da30b74876
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248533"
---
# <a name="how-to-configure-a-wcf-customisolated-receive-handler"></a>如何配置 WCF-CustomIsolated 接收处理程序
如果希望 WCF-CustomIsolated 适配器在 machine.config 以外的位置查找自定义行为扩展，则必须配置接收处理程序属性。  
  
## <a name="why-should-wcf-customisolated-adapter-look-up-custom-behavior-extensions-from-locations-other-than-machineconfig"></a>为什么 WCF-CustomIsolated 适配器应从 machine.config 以外的位置查找自定义行为扩展？  
 使用自定义行为扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 machine.config 中注册。加载行为扩展之前, 的 WCF CustomIsolated 适配器查找 machine.config 中的行为扩展。但是，理想情况下用于 machine.config 存储在特定计算机上运行的所有应用程序所需的配置信息。 另一方面，WCF 自定义行为扩展可能需要仅通过[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而不是在计算机上运行的所有应用程序。 因此，虽然在 machine.config 中存储的自定义行为扩展用途，它不是最大程度优化的位置。  
  
 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，适配器处理程序属性提供了 WCF-CustomIsolated 适配器可以从中查找自定义行为扩展的其他位置。 请注意这不会替换已在 machine.config 中提供的行为扩展。  
  
### <a name="additional-considerations"></a>其他注意事项  
 保留以下配置 WCF CustomIsolated 时点记住接收处理程序属性：  
  
-   自定义行为扩展必须在 machine.config 或适配器处理程序属性中可用。 在这两个位置中必须不能重复的自定义行为扩展。  
  
-   如果您尝试设置适配器处理程序属性的相同行为扩展的自定义行为扩展已在 machine.config 中可用，你会收到错误，就会立即尝试设置属性。  
  
-   如果已经为适配器处理程序属性设置了自定义行为扩展，然后用同样的行为扩展更新 machine.config 时，会收到运行时错误，并且还会在事件日志中记录此错误。 接收位置也被禁用。  
  
-   设置适配器处理程序属性之前，必须存在在全局程序集缓存 (GAC) 中的自定义行为扩展所引用的程序集。  
  
## <a name="configuring-the-adapter-handler-properties"></a>配置适配器处理程序属性  
 使用以下过程来配置 WCF CustomIsolated 接收处理程序。  
  
#### <a name="to-configure-the-adapter-handler-properties"></a>若要配置的适配器处理程序属性  
  
1.  在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2.  在展开的适配器列表中，单击**WCF CustomIsolated**，而是在右窗格中，右键单击你想要配置，接收处理程序，然后单击**属性**。  
  
3.  在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将与之相关联，该主机，然后单击**属性**。  
  
4.  在**WCF CustomIsolated 传输属性**对话框中，在**WCF 扩展**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**导入**|导入带有 WCF 自定义行为扩展的 WCF 配置文件。 单击此按钮将打开**导入 WCF 配置**对话框中浏览并找到 WCF 配置文件。 请注意，该文件应是有效的 WCF 配置文件。 有关 WCF 配置架构的详细信息，请参阅"Windows Communication Foundation 配置架构"在[http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953)。|  
    |**导出**|将 WCF 自定义行为扩展导出到 WCF 配置文件。 单击此按钮将打开**导出 WCF 配置**对话框中，以浏览并保存 WCF 配置文件。|  
    |**Clear**|清除适配器处理程序属性中的现有 WCF 自定义行为扩展。|  
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF CustomIsolated 适配器](../core/configuring-the-wcf-customisolated-adapter.md)