---
title: AS2 发送方实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e2a88fc-67fd-4801-a6f8-1e7c92098eaf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37a6c7ea0500b24db9a99d94ea4044a0d645b134
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358859"
---
# <a name="as2-sender-utility"></a>AS2 发送方实用工具
AS2 发送方实用工具随[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可将 AS2 消息发送到一台计算机上的网站。 此实用程序模拟从单独的计算机上发送的 AS2 消息。  
  
 AS2 发送方实用工具文件位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
## <a name="what-this-utility-does"></a>此实用程序的用途  
 AS2 发送方实用工具生成带有 EDI 负载的 AS2 消息，并将该消息发送到使用 BTSHTTPReceive ISAPI 筛选器的 Web 站点。 默认情况下本教程将执行以下操作：  
  
- 将发送带有 864 X12 编码的负载名为 X12_00401_864.edi 的 AS2 消息。 此消息位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial 文件夹。  
  
- 将提示一个异步 MDN 以响应 AS2 消息。 这由发送，该消息，可以更改。  
  
- 将 AS2 消息发送到接收位置通过 Contoso 虚拟目录。  
  
  可以修改该实用工具以更改此特定行为。 请参阅[如何自定义 AS2 发送方实用工具](../core/as2-sender-utility.md#BKMK_Custom)下面一节。  
  
## <a name="how-to-set-up-a-solution-using-the-as2-sender-utility"></a>如何设置解决方案，使用 AS2 发送方实用工具  
 若要设置为使用 AS2 发送方实用工具的一个解决方案，需要执行以下操作。  
  
> [!IMPORTANT]
>  在 AS2 教程和两个 AS2 发送方演练中演示了这些步骤。 有关详细信息，请参阅[教程 3:AS2 教程](../core/tutorial-3-as2-tutorial.md)，[演练 (AS2):使用同步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)，和[演练 (AS2):使用异步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)。  
  
-   启用 BTSHTTPReceive ISAPI 筛选器。  
  
-   配置 Web 页面，以接收 AS2 消息的接收位置。 中默认的 AS2 发送方实用工具，该网页是 Contoso 网页。  
  
-   部署将作为有效负载的 AS2 消息发送 EDI 交换的架构。  
  
-   设置相应的 AS2 和 EDI 参与方属性。  
  
##  <a name="BKMK_Custom"></a> 如何自定义 AS2 发送方实用工具  
 默认的 AS2 发送方实用工具通过 AS2 发送一个测试 864 EDI 交换到 Contoso 网页上使用 BTSHTTPReceive ISAPI 筛选器。 名为 X12_00401_864.edi 的 AS2 消息提示一个异步 MDN。 AS2 发送方实用工具代码位于 httpsender.cs 中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]AS2 Tutorial\Sender 文件夹。 在 HttpSender.cs 中的代码的以下行发送默认 864 测试文件：  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
```  
  
> [!NOTE]
>  您可以修改此行具有不同的文件名称和不同的路径。  
  
 在 HttpSender.cs 中的以下行发送名为 X12_00401_864-Sync.edi 的 AS2 消息。 此消息会提示同步 MDN。 默认情况下，这行代码在 HttpSender.cs 中是为了支持发送 X12_00401_864.edi 行注释掉。 若要发送 X12_00401_864-Sync.edi，取消注释 X12_00401_864-Sync.edi 行并注释掉 X12_00401_864.edi 行。  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
```  
  
 HttpSender.cs 中的代码的下一行将消息发送到 Contoso 网页：  
  
```  
HttpSender TestSender = new HttpSender("http://localhost/Contoso/BTSHttpReceive.dll");  
```  
  
> [!NOTE]
>  您可以修改此行使用不同的虚拟目录和 ISAPI 筛选器。  
  
### <a name="to-build-the-as2-sender-sample"></a>生成 AS2 发送方示例  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开中的 Sender.csproj 项目[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender 文件夹。  
  
2. 在发送方项目中，打开 HttpSender.cs 和自定义的发件人代码与相应的接收网页和 EDI 文件名和路径。  
  
3. 右键单击 Sender 项目，然后单击**属性**。  
  
4. 单击**签名**左侧控制台中。 絋粄**为程序集签名**已选中和强名称密钥文件设置为**Sender.snk**。 请确保**仅延迟签名**清除。  
  
5. 生成项目。  
  
### <a name="to-run-the-as2-sender-sample"></a>若要运行 AS2 发送方示例  
  
1. 打开命令提示符。 将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug。  
  
2. Enter **Sender.exe**，然后按**Enter**。  
  
3. 验证看到一条消息，该值指示已成功发送的 AS2 消息，然后关闭命令提示符。  
  
## <a name="see-also"></a>请参阅  
 [教程 3：AS2 教程](../core/tutorial-3-as2-tutorial.md)   
 [演练 (AS2):使用同步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)   
 [演练 (AS2):使用异步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)