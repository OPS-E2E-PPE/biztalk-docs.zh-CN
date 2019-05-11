---
title: 如何配置 Wcf-custom 接收处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0208a7aa-6e42-43b7-a934-27ef4409b4ec
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a24977805f9d55ec95784a81a2a2c914d887f440
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342268"
---
# <a name="how-to-configure-a-wcf-custom-receive-handler"></a>如何配置 Wcf-custom 接收处理程序
如果你想，则必须配置接收处理程序属性[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)]从 machine.config 之外的位置查找自定义行为扩展。  
  
## <a name="why-should-wcf-custom-adapter-lookup-custom-behavior-extensions-from-locations-other-than-machineconfig"></a>为什么应 machine.config 以外的位置从 WCF 自定义适配器查找自定义行为扩展？  
 使用的自定义行为扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 machine.config 中注册。加载行为扩展之前[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)]行为扩展在 machine.config 中查找。但是，machine.config 最好用于存储在特定计算机上运行的所有应用程序所需的配置信息。 但是，WCF 自定义行为扩展可能需要只能由[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而不是由在计算机上运行的所有应用程序。 因此，尽管在 machine.config 中存储自定义行为扩展用途，它不是最佳的位置。  
  
 与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，适配器处理程序属性提供的其他位置[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)]可以查找自定义行为扩展。 请注意这不会替换已在 machine.config 中提供的行为扩展。  
  
### <a name="additional-considerations"></a>其他注意事项  
 以下几点记住配置 WCF 自定义时接收处理程序属性：  
  
-   自定义行为扩展必须在 machine.config 或适配器处理程序属性中可用。 不能在这两个位置复制自定义行为扩展。  
  
-   如果已在 machine.config 中提供自定义行为扩展，并且您尝试设置适用于适配器处理程序属性的相同行为扩展，只要您尝试设置该属性可能会出错。  
  
-   如果自定义行为扩展已经安装的适配器处理程序属性，然后使用相同的行为扩展更新 machine.config，将获取运行时错误，它还会在事件日志中记录。 接收位置也被禁用。  
  
-   设置适配器处理程序属性之前，在自定义行为扩展中引用的程序集必须在全局程序集缓存 (GAC) 中存在。  
  
## <a name="configuring-the-adapter-handler-properties"></a>配置适配器处理程序属性  
 使用此主题，以配置 WCF 自定义中的过程接收处理程序。  
  
#### <a name="to-configure-the-adapter-handler-properties"></a>若要配置适配器处理程序属性  
  
1. 在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2. 在展开的适配器列表中，单击**WCF 自定义**，在右窗格中，右键单击你想要配置，接收处理程序，再单击**属性**。  
  
3. 在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将关联的主机，然后单击**属性**。  
  
4. 在中**Wcf-custom 传输属性**对话框中，在**WCF 扩展**选项卡上，执行以下操作：  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**导入**|导入 WCF 配置文件与 WCF 自定义行为扩展。 单击此按钮将打开**导入 WCF 配置**对话框可以浏览并找到 WCF 配置文件。 请注意该文件应是有效的 WCF 配置文件。 有关 WCF 配置架构的详细信息，请参阅"Windows Communication Foundation 配置架构"处[ http://go.microsoft.com/fwlink/?LinkId=163953 ](http://go.microsoft.com/fwlink/?LinkId=163953)。|  
   |**导出**|将 WCF 自定义行为扩展导出到 WCF 配置文件。 单击此按钮将打开**导出 WCF 配置**对话框，游览并保存 WCF 配置文件。|  
   |**Clear**|清除适配器处理程序属性中的现有 WCF 自定义行为扩展。|  
  
## <a name="see-also"></a>请参阅  
 [配置 WCF-Custom 适配器](../core/configuring-the-wcf-custom-adapter.md)