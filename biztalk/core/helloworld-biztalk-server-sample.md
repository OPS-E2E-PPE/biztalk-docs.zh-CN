---
title: "HelloWorld （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, messages
ms.assetid: 4416029a-ca76-45a4-b66c-b44cb71ded58
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e70271967086f530ce5421348c118a74019dd366
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="helloworld-biztalk-server-sample"></a>HelloWorld （BizTalk Server 示例）
HelloWorld 示例演示如何使用 BizTalk 业务流程将 XML 消息（采购订单）转换为相关但不同类型的消息（发票）。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例配置**中**接收位置的文件夹。 当您放置文件，如示例文件**SamplePOInput.xml**，到此文件夹中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理消息使用以下步骤：  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 从接收位置文件夹检索 XML 采购订单消息。  
  
2.  业务流程使用映射文件从 XML 采购订单创建 XML 发票。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成的 XML 发票消息放入发送适配器**出**文件夹。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 在公司间消息交换方案中，经常需要将从贸易合作伙伴接收的入站消息转换为内部应用程序可以识别的格式。 此示例使用**接收**形状，**转换**形状，和一个**发送**形状以获得此结果。 **转换**形状在此示例中扮演重要角色，因为它是消息格式转换的出现位置。 拖动**转换**调整到您的业务流程和为其配置的源消息、 映射名称和目标消息。 在运行期间，使用您指定的映射将源消息映射到目标消息。  
  
 有关详细信息**转换**形状，请参阅[如何配置转换形状](../core/how-to-configure-the-transform-shape.md)。 有关生成地图的详细信息，请参阅[创建地图使用 BizTalk 映射程序](../core/creating-maps-using-biztalk-mapper.md)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Orchestrations\HelloWorld\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|HelloOrchestration.odx|对采购订单转换为发票进行协调的业务流程。|  
|HelloWorld.btproj、HelloWorld.sln|本示例的项目文件和解决方案文件。|  
|HelloWorldBinding.xml|用于如端口绑定之类的自动化设置。|  
|InvoiceSchema.xsd、POSchema.xsd|分别用于发票和采购订单消息的架构。|  
|POToInvoice.btm|将采购订单转换为发票的映射。|  
|SamplePOInput.xml|示例输入文件。|  
|Setup.bat|用于生成和初始化本示例。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-helloworld-sample"></a>生成并初始化 HelloWorld 示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Orchestrations\HelloWorld  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   在下面的文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹：  
  
         \<*示例路径*\>\Orchestrations\HelloWorld  
  
    -   编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例项目。  
  
    -   创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口，并将它们绑定到业务流程。  
  
    -   启用接收位置并启动发送端口。 登记，并启动业务流程。  
  
> [!NOTE]
>  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。 通过查看事件日志可以确认这一点。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-helloworld-sample"></a>运行 HelloWorld 示例  
  
1.  将文件 SamplePOInput.xml 的副本粘贴到**中**文件夹。  
  
2.  观察在中创建的.xml 文件**出**文件夹。 此文件包含从输入文件 SamplePOInput.xml 构造 XML 发票。 此文件的名称的格式是\< *MessageID*\>.xml，其中 *\<MessageID\>*  GUID 生成以唯一标识消息.  
  
## <a name="uninstalling-this-sample"></a>卸载本示例  
  
#### <a name="to-uninstall-the-helloworld-sample"></a>卸载 HelloWorld 示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Orchestrations\HelloWorld\  
  
2.  运行 Cleanup.bat。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程（BizTalk Server 示例文件夹）](../core/orchestrations-biztalk-server-samples-folder.md)