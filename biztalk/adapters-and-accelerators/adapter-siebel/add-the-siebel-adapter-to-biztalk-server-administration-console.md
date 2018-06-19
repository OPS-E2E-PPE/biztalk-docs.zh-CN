---
title: 将 Siebel 适配器添加到 BizTalk Server 管理控制台 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b64d0bdc-ac83-46c9-b27d-625088a013d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb4a946c9fd987c1a97fa24a9b50d3cdf2f7d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217277"
---
# <a name="add-the-siebel-adapter-to-biztalk-server-administration-console"></a>将 Siebel 适配器添加到 BizTalk Server 管理控制台
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以在 BizTalk 中作为 WCF 自定义端口或 WCF Siebel 端口使用。 如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF 自定义端口，你不需要添加到的 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]默认情况下的管理控制台。 但是，如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF Siebel 端口，您必须首先添加到在 WCF Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 本主题将说明了如何将添加到在 WCF Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!IMPORTANT]
>  如果你想要配置的 WCF 自定义端口，则不需要执行这些任务[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
## <a name="add-the-siebel-adapter"></a>添加 Siebel 适配器  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
3.  右键单击**适配器**，指向**新建**，然后单击**适配器**。  
  
     ![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4.  在**适配器属性**对话框框中，指定的名称为适配器并从**适配器**列表中，选择**WCF Siebel**。  
  
     ![添加 WCF &#45;Siebel 适配器到 BizTalk 控制台](../../adapters-and-accelerators/adapter-siebel/media/6d39b874-2233-452a-81ef-d93274b0784c.gif "6d39b874-2233-452a-81ef-d93274b0784c")  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
[构建基块创建带有 Siebel 适配器 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)