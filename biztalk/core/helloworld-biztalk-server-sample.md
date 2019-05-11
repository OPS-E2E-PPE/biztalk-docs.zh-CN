---
title: HelloWorld （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, messages
ms.assetid: 4416029a-ca76-45a4-b66c-b44cb71ded58
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3d26c006c7752b5e2ef2480cff3b57457f4dbfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387571"
---
# <a name="helloworld-biztalk-server-sample"></a>HelloWorld （BizTalk Server 示例）
HelloWorld 示例演示如何使用 BizTalk 业务流程将 XML 消息 （采购订单） 转换为相关但不同的消息 （发票） 的类型。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例配置**在**与接收位置的文件夹。 当将一个文件，如示例文件**SamplePOInput.xml**，到此文件夹中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]按照以下步骤处理该消息：  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 从接收位置文件夹检索 XML 采购订单消息。  
  
2. 业务流程使用映射文件从 XML 采购订单创建 XML 发票。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将生成的 XML 发票消息放入发送适配器**出**文件夹。  
  
## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 在公司间的消息交换方案中，通常很有必要，将从为内部应用程序可以识别的格式贸易合作伙伴接收的入站的消息。 此示例使用**接收**形状**转换**形状，和一个**发送**形状来实现此目标。 **转换**形状在此示例中扮演重要角色，因为它是消息格式转换发生的地方。 您拖动**转换**形状在业务流程，然后为其配置源消息、 映射名称和目标消息。 在运行时，将源消息通过使用指定的映射映射到目标消息。  
  
 有关详细信息**转换**形状中，请参阅[如何配置转换形状](../core/how-to-configure-the-transform-shape.md)。 有关构建映射的详细信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*Samples Path*\>\Orchestrations\HelloWorld\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|HelloOrchestration.odx|业务流程的采购订单转换为发票进行协调。|  
|HelloWorld.btproj, HelloWorld.sln|本示例的项目和解决方案文件。|  
|HelloWorldBinding.xml|用于如端口绑定之类的自动化设置。|  
|InvoiceSchema.xsd, POSchema.xsd|有关发票和采购订单消息的架构，分别。|  
|POToInvoice.btm|用于将采购订单转换为发票的映射。|  
|SamplePOInput.xml|示例输入的文件。|  
|Setup.bat|用于生成和初始化本示例。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-helloworld-sample"></a>若要生成并初始化 HelloWorld 示例  
  
1. 在命令窗口中，导航到以下文件夹：  
  
    \<*Samples Path*\>\Orchestrations\HelloWorld  
  
2. 运行文件 Setup.bat，以执行以下操作：  
  
   - 创建输入 (In) 和输出 (Out) 文件夹中，为此示例的以下文件夹：  
  
      \<*Samples Path*\>\Orchestrations\HelloWorld  
  
   - 编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例项目。  
  
   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收到业务流程的端口。  
  
   - 启用该接收位置，并启动发送端口。 登记并启动业务流程。  
  
> [!NOTE]
>  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。 你可以通过查看事件日志来确认这一点。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-helloworld-sample"></a>若要运行 HelloWorld 示例  
  
1.  将文件 SamplePOInput.xml 的副本粘贴到**在**文件夹。  
  
2.  查看在中创建的.xml 文件**出**文件夹。 此文件包含从输入文件 SamplePOInput.xml 构造的 XML 发票。 此文件的名称的格式\< *MessageID*\>.xml，其中*\<MessageID\>* 生成的 GUID 来唯一标识消息.  
  
## <a name="uninstalling-this-sample"></a>卸载本示例  
  
#### <a name="to-uninstall-the-helloworld-sample"></a>卸载 HelloWorld 示例  
  
1.  在命令窗口中，导航到以下文件夹：  
  
     \<*Samples Path*\>\Orchestrations\HelloWorld\  
  
2.  运行 Cleanup.bat。  
  
## <a name="see-also"></a>请参阅  
 [业务流程（BizTalk Server 示例文件夹）](../core/orchestrations-biztalk-server-samples-folder.md)