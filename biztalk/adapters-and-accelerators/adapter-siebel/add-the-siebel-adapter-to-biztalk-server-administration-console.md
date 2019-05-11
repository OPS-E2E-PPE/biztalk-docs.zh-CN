---
title: 将 Siebel 适配器添加到 BizTalk Server 管理控制台 |Microsoft Docs
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
ms.openlocfilehash: c2d913cf980790f7df1a39411295d13bdf59c78c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372087"
---
# <a name="add-the-siebel-adapter-to-biztalk-server-administration-console"></a>将 Siebel 适配器添加到 BizTalk Server 管理控制台
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以在 BizTalk 中可作为 WCF 自定义端口或 Wcf-siebel 端口使用。 如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF 自定义端口，您不需要添加到 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的默认情况下。 但是，如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF Siebel 端口，必须首先添加 Wcf-siebel 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 本主题说明了如何添加 Wcf-siebel 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!IMPORTANT]
>  如果你想要配置 WCF 自定义端口，则不需要执行这些任务[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
## <a name="add-the-siebel-adapter"></a>将 Siebel 适配器添加  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
3. 右键单击**适配器**，依次指向**新建**，然后单击**适配器**。  
  
    ![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. 在中**适配器属性**对话框框中，指定名称的适配器，从**适配器**列表中，选择**Wcf-siebel**。  
  
    ![添加 WCF&#45;Siebel 适配器添加到 BizTalk 控制台](../../adapters-and-accelerators/adapter-siebel/media/6d39b874-2233-452a-81ef-d93274b0784c.gif "6d39b874-2233-452a-81ef-d93274b0784c")  
  
5. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
[若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)