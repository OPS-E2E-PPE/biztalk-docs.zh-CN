---
title: 第 1 步：EDI 接口开发人员教程的准备工作 |Microsoft Docs
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
ms.openlocfilehash: d01678bb342909d13beb15141765b789b12a0687
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392799"
---
# <a name="step-1-prepare-for-the-edi-interface-developer-tutorial"></a>第 1 步：EDI 接口开发人员教程的准备工作
![步骤 1 部分，共 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")  
  
 EDI 接口开发人员教程运行在单台计算机上。 若要准备本教程，必须安装和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中所述[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。 您还必须添加对 BizTalk EDI 应用程序的引用  
  
> [!NOTE]
>  若要运行本教程，必须使用 IIS 7.5 或 IIS 8 的平台上运行它。  
  
 EDI 接口开发人员教程所需的文件位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial 文件夹。 文件夹和教程所需的文件如下所示：  
  
|Folder\File|用途|  
|------------------|-------------|  
|\SDK\EDI 接口开发人员 Tutorial\EDI 入站 Processing.sln|使用 Visual Studio 中创建此消息传递方案的解决方案文件|  
|\SDK\EDI 接口开发人员 Tutorial\keyfile.snk|指定解决方案文件的程序集密钥文件|  
|\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\SamplePO.txt|示例消息文件 （版本 4010 850），用来测试解决方案|  
|\SDK\EDI 接口开发人员 Tutorial\ Inbound_EDI\Inbound4010850_to_OrderFile.btm|BizTalk 映射，可将 850 消息数据转换为订单系统所需的格式。|  
|\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\SendOrderFilePipeline.btp|处理测试消息以将消息发送到订单系统的发送管道。|  
|\SDK\EDI 接口开发人员 Tutorial\ Inbound_EDI\X12_00401_850.xsd|测试消息的 850 架构。|  
\SDK\EDI interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\fromTHEM|从 Fabrikam 接收入站 850 消息所在的文件夹|  
|\SDK\EDI 界面开发人员 Tutorial\ ProcessEDI_TestLocations\Scenario A\toOrderSystem|其中的出站 850 消息发送到的文件夹表示订单系统后端应用程序|  
|\SDK\EDI 接口开发人员 Tutorial\ ProcessEDI_TestLocations\Scenario A\toTHEM_997|文件夹位置将 997 确认发送到代表 Fabrikam|  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-add-reference-to-the-biztalk-edi-application"></a>若要添加到 BizTalk EDI 应用程序的引用  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**应用程序**节点，右键单击你想要为 EDI，如 BizTalk Application 1 使用的应用程序。 指向**添加**，然后单击引用。  
  
2. 在中**添加应用程序引用**对话框中，选择**BizTalk EDI 应用程序**，然后单击**确定**。  
  
## <a name="next-steps"></a>后续步骤  
 生成并部署 Inbound_EDI 程序集，如中所述[步骤 2:更新和部署教程解决方案](../core/step-2-update-and-deploy-the-tutorial-solution.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 2：EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md)