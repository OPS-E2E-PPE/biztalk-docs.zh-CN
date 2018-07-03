---
title: DynamicReceive 示例 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fa7c934-7ec3-45ad-b226-c8c53934ecb1
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af89bac79614268f4648f688d8cabfc913ed2277
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974126"
---
# <a name="dynamicreceive-sample-biztalk-server-sample"></a>DynamicReceive 示例（BizTalk Server 示例）
DynamicReceive 示例演示如何接收[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来自 MQSeries 的消息队列时动态指定 MQSeries 队列的 URI。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例将动态创建 MQSeries 队列由指定**queueManager**，**队列**，并**server**变量。 启用动态接收方案并获取[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]动态指定 MQSeries 队列中的消息基于中指定的筛选器条件**MQMD_MsgId**并**MQMD_CorrelId**消息属性。  
  
## <a name="how-this-sample-was-designed-and-why"></a>本示例的设计方式和原因  
 通过在业务流程中指定 MQSeries 队列的 URI 地址，MQSeries 适配器即可从该队列动态接收消息。 此功能可通过在业务流程中使用要求-响应发送端口来获得。  
  
 若要动态接收消息，指定以下**表达式**形状在业务流程中：  
  
1. 启用动态接收通过设置以下属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息： **MQSeries.DynamicReceive** = `'Yes'`  
  
2. 指定要从其中获取消息通过设置 URI 的端口地址。 （可选） 你可以指定以下项：  
  
   -   使用获取消息之前指定的等待时间间隔**MQSeries.WaitInterval**消息属性。  
  
   -   指定用于接收消息的匹配条件。 匹配条件选项包括**消息 ID**， **CorrelationID**， **GroupID**，以及**MessageSequenceNumber**。 请参阅"属性相关到 BizTalk Server"，网址[ http://go.microsoft.com/fwlink/?LinkId=89396 ](http://go.microsoft.com/fwlink/?LinkId=89396)的更多详细信息。  
  
   将创建具有这些属性的消息后它是使用要求响应发送端口发送到 MQSeries 队列。 端口指定从指定的 URI 所指示的匹配选项接收消息的适配器。 下面的操作结果：  
  
- 如果满足筛选条件来获取一条消息，消息从队列检索，并且发送回业务流程。  
  
- 如果不满足筛选条件来获取一条消息，则返回一个虚拟响应。 这是指定的选项未返回任何消息队列中的指示。  
  
  使用动态接收更加灵活地因为固定的接收位置不是必需的功能提供。 在某些情况下，可能不知道到运行时的 URI。 动态接收功能，您可以动态确定从何处可以获取消息。 这还意味着不需要实现业务流程中的排队协定。  你可以等待可以通过使用动态指定从指定的匹配条件的 MQSeries 队列的 URI 中获取消息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive  
  
 下表显示了本示例中的文件及其用途说明：  
  
|||  
|-|-|  
|文件|Description|  
|DynamicReceive.btproj，<br /><br /> DynamicReceive.sln|应用程序的项目和解决方案文件。|  
|DynamicReceive e.odx|应用程序的 BizTalk 业务流程文件。|  
|Setup.bat|若要创建的密钥文件、 编译该项目，并将其部署的批处理文件。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 指定**Microsoft.XLANGs.BaseTypes.Address**适合你的解决方案。 更改**MQSeries.WaitInterval**以指定希望接收响应消息。 更新 （或添加） 的匹配选项，或删除它们，如果你打算中获取所有消息。  
  
## <a name="building-and-running-the-sample"></a>构建和运行示例  
  
#### <a name="to-create-the-sample"></a>若要创建示例  
  
1. 在 Microsoft 中创建一个新的业务流程项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2. 通过设置可启用动态接收操作**MQSeries.DynamicReceive**上的属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息到`'Yes'`。  
  
3. 指定要从中获取消息的设置的地址**端口 URI**。  
  
4. （可选） 可以指定以下两个属性：  
  
   1.  使用获取消息之前，指定等待间隔**MQSeries.WaitInterval**消息属性。  
  
   2.  指定用于接收消息的匹配条件。 有关详细信息，请参阅“匹配选项”帮助。  
  
5. 更改业务流程，以指定从中获取从消息中的以下变量：  
  
   -   **队列**， **queueManager**，和**server**。 这些用于生成该 URI**表达式**形状。  
  
6. 修改**表达式**形状中，以根据需要添加注释动态队列创建和匹配选项。  
  
7. 可生成和部署项目中，以下两种方式：  
  
   -   打开解决方案，右键单击解决方案资源管理器中的项目，然后单击**属性**查看项目属性。 在签名选项卡上单击**\<新建...\>** 中**选择一个强名称密钥文件**下拉框。 然后提供密钥文件名称和部署。  
  
   -   或者，运行 setup.bat 文件创建密钥文件，生成项目，并将其部署。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  将业务流程绑定到 BizTalk 主机。  
  
2.  启用业务流程创建的文件接收端口。 将文件接收位置从**c:\temp\in**到正确的文件的文件夹。  
  
3.  登记并启动已创建的两个发送端口。 一个端口是动态要求响应端口类型，另一个是文件发送端口且是用于发送消息的队列。 确保已将此设置为正确的位置。  
  
4.  若要启动该业务流程，请将一个文件放在输入文件夹中。 这将调用 MQSeries 适配器并调用**MQSAgent2** COM + 组件上指定的服务器以获取消息。 接收到的消息将存储在文件发送端口中指定的文件夹位置。  
  
5.  如果未找到消息中指定的条件匹配的**表达式**形状，一个虚拟消息放入输出文件夹。 若要禁用匹配选项，将最后两个行中注释掉**表达式**形状。  
  
## <a name="comments"></a>注释  
  
-   如果正在动态创建队列但未删除，则该队列将在下一个业务流程实例激活时引发错误。  
  
-   还可通过其他方法动态设置 URI，此示例只指定了一个选项。 例如，可在消息上下文中读取某些属性来设置 URI。  
  
-   如果队列中没有满足匹配选项的消息，则将返回一个虚拟消息。  
  
-   由于此示例使用动态发送端口，因此，可能需要指定诸如重试和事务等其他选项。 使用由适配器公开的上下文属性，可在将消息发送到动态要求-响应端口前设置这些选项。  
  
-   可以创建和使用动态删除 MQSeries 队列**MQSAdapterAdmin2**接口。 如何动态创建 MQSeries 队列的示例，请参阅"支持的队列管理"在[ http://go.microsoft.com/fwlink/?LinkId=89400 ](http://go.microsoft.com/fwlink/?LinkId=89400)。