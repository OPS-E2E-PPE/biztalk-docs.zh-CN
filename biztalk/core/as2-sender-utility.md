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
ms.openlocfilehash: d2b07b2d791f4870b608e552189cd2f35754c950
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998214"
---
# <a name="as2-sender-utility"></a>AS2 发送方实用工具
AS2 发送方实用工具与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起提供，允许您向某一计算机上的网站发送 AS2 消息。 此实用工具可模拟从单独的计算机发送 AS2 消息的过程。  
  
 AS2 发送方实用工具文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender 中。  
  
## <a name="prerequisites"></a>必要條件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
## <a name="what-this-utility-does"></a>此实用程序的用途  
 AS2 发送方实用工具生成一个带有 EDI 负载的 AS2 消息，并将该消息发送到使用 BTSHTTPReceive ISAPI 筛选器的网站。 默认情况下，此教程将执行以下操作：  
  
- 发送一个带有 864 X12 编码的负载的名为 X12_00401_864.edi 的 AS2 消息。 此消息位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial 文件夹中。  
  
- 提示一个异步 MDN 以响应该 AS2 消息。 这是由发送的消息确定的，可进行更改。  
  
- 将该 AS2 消息通过 Contoso 虚拟目录发送到一个接收位置。  
  
  可修改该实用工具以更改此特定行为。 请参阅[如何自定义 AS2 发送方实用工具](../core/as2-sender-utility.md#BKMK_Custom)下面一节。  
  
## <a name="how-to-set-up-a-solution-using-the-as2-sender-utility"></a>如何使用 AS2 发送方实用工具设置解决方案  
 若要设置一个解决方案以使用 AS2 发送方实用工具，需要执行下列操作。  
  
> [!IMPORTANT]
>  这些步骤在 AS2 教程和两个 AS2 发送方演练中进行演示。 有关详细信息，请参阅[教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)，[演练 (AS2): 使用同步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)，和[演练 (AS2): 使用异步通过 AS2 发送 EDIMDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)。  
  
-   启用 BTSHTTPReceive ISAPI 筛选器。  
  
-   配置网页和接收位置以接收 AS2 消息。 在默认的 AS2 发送方实用工具中，该网页是 Contoso 网页。  
  
-   部署您将作为 AS2 消息的负载进行发送的 EDI 交换的架构。  
  
-   设置相应的 AS2 和 EDI 参与方属性。  
  
##  <a name="BKMK_Custom"></a> 如何自定义 AS2 发送方实用工具  
 默认的 AS2 发送方实用工具通过 AS2 将一个测试 864 EDI 交换发送到一个使用 BTSHTTPReceive ISAPI 筛选器的 Contoso 网页。 名为 X12_00401_864.edi 的 AS2 消息将提示一个异步 MDN。 AS2 发送方实用工具代码位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] AS2 Tutorial\Sender 文件夹中的 HttpSender.cs 中。 HttpSender.cs 中的以下代码行用于发送默认 864 测试文件：  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
```  
  
> [!NOTE]
>  您可使用其他文件名和其他路径来修改此行。  
  
 在 HttpSender.cs 中的以下行发送名为 X12_00401_864-Sync.edi 的 AS2 消息。 此消息将提示一个异步 MDN。 默认情况下，HttpSender.cs 中的此代码行是被注释掉的，以利于执行用于发送 X12_00401_864.edi 的代码行。 若要发送 X12_00401_864-Sync.edi，取消 X12_00401_864-Sync.edi 行的注释并注释掉 X12_00401_864.edi 行。  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
```  
  
 HttpSender.cs 中的以下代码行用于将消息发送到 Contoso 网页：  
  
```  
HttpSender TestSender = new HttpSender("http://localhost/Contoso/BTSHttpReceive.dll");  
```  
  
> [!NOTE]
>  您可使用其他虚拟目录和 ISAPI 筛选器来修改此行。  
  
### <a name="to-build-the-as2-sender-sample"></a>生成 AS2 发送方示例  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender 文件夹中的 Sender.csproj 项目。  
  
2. 打开发送方项目中的 HttpSender.cs，使用适当的接收网页和 EDI 文件名和路径自定义发送方代码。  
  
3. 右键单击 Sender 项目，然后单击**属性**。  
  
4. 单击**签名**左侧控制台中。 絋粄**为程序集签名**已选中和强名称密钥文件设置为**Sender.snk**。 请确保**仅延迟签名**清除。  
  
5. 生成此项目。  
  
### <a name="to-run-the-as2-sender-sample"></a>运行 AS2 发送方示例  
  
1. 打开命令提示符。 移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug。  
  
2. Enter **Sender.exe**，然后按**Enter**。  
  
3. 验证你已看到一条消息，指出 AS2 消息已成功发送，然后关闭命令提示符窗口。  
  
## <a name="see-also"></a>请参阅  
 [教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)   
 [演练 (AS2): 使用同步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)   
 [演练 (AS2)：使用异步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)