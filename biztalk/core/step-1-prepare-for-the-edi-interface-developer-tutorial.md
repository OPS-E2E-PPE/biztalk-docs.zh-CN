---
title: 步骤 1： 准备 EDI 接口开发人员教程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9be1bddf-d673-4054-87f5-0205b8b5cc0d
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b222e425f44e58d79ab65d848a7aff395b1284b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279229"
---
# <a name="step-1-prepare-for-the-edi-interface-developer-tutorial"></a>步骤 1： 准备 EDI 接口开发人员教程
![9 的第 1 步](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")  
  
 EDI 接口开发人员教程运行在单台计算机上。 若要准备本教程，你必须安装和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中所述[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。 你还必须添加到 BizTalk EDI 应用程序的引用  
  
> [!NOTE]
>  对于本教程中工作，必须在使用 IIS 7.5 或 IIS 8 平台上运行它。  
  
 EDI 接口开发人员教程所需的文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial 文件夹中。 此教程所需的文件夹和文件如下所示：  
  
|文件夹\文件|用途|  
|------------------|-------------|  
|\SDK\EDI Interface Developer Tutorial\EDI Inbound Processing.sln|在 Visual Studio 中，使用该解决方案文件可创建此消息传送方案|  
|\SDK\EDI Interface Developer Tutorial\keyfile.snk|为解决方案文件指定的程序集密钥文件|  
|\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\SamplePO.txt|示例消息文件（版本 4010 850），可用于测试解决方案|  
|\SDK\EDI 接口开发人员 Tutorial\ Inbound_EDI\Inbound4010850_to_OrderFile.btm|BizTalk 映射，可将 850 消息数据转换为订单系统所需的格式。|  
|\SDK\EDI 接口开发人员 Tutorial\ Inbound_EDI\SendOrderFilePipeline.btp|发送管道，用于处理测试消息以将该消息发送到订单系统。|  
|\SDK\EDI 接口开发人员 Tutorial\ Inbound_EDI\X12_00401_850.xsd|测试消息的 850 架构。|  
\SDK\EDI 接口开发人员 Tutorial\ ProcessEDI_TestLocations\Scenario A\fromTHEM|用于接收来自 Fabrikam 的入站 850 消息的文件夹|  
|\SDK\EDI 接口开发人员 Tutorial\ ProcessEDI_TestLocations\Scenario A\toOrderSystem|用来接收出站 850 消息的文件夹，代表订单系统后端应用程序|  
|\SDK\EDI 接口开发人员 Tutorial\ ProcessEDI_TestLocations\Scenario A\toTHEM_997|用于接收 997 确认的文件夹，代表 Fabrikam|  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-add-reference-to-the-biztalk-edi-application"></a>若要添加到 BizTalk EDI 应用程序的引用  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，在**应用程序**节点，右键单击你想要使用 EDI，如 BizTalk 应用程序 1 的应用。 指向**添加**，，然后单击引用。  
  
2.  在**添加应用程序引用**对话框中，选择**BizTalk EDI 应用程序**，然后单击**确定**。  
  
## <a name="next-steps"></a>后续步骤  
 生成并部署 Inbound_EDI 程序集中, 所述[步骤 2： 更新并将其部署该教程解决方案](../core/step-2-update-and-deploy-the-tutorial-solution.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 2: EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md)