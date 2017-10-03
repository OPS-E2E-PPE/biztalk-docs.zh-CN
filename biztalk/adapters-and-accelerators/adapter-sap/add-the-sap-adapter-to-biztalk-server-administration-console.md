---
title: "将 SAP 适配器添加到 BizTalk Server 管理控制台 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95fc925d-0aac-4f0d-a19d-ad27469e4b3c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19870e69dc502f9635f34b578c2853aaf8897e00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="add-the-sap-adapter-to-biztalk-server-administration-console"></a>将 SAP 适配器添加到 BizTalk Server 管理控制台
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以在 BizTalk 中作为 WCF 自定义端口或 WCF SAP 端口使用。 如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF 自定义端口，你不需要添加到的 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]默认情况下的管理控制台。 但是，如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF SAP 端口，您必须首先添加到 WCF SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 本主题将说明了如何将添加到 WCF SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!IMPORTANT]
>  如果你想要配置的 WCF 自定义端口，则不需要执行这些任务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="add-the-sap-adapter"></a>添加 SAP 适配器  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
3.  右键单击**适配器**，指向**新建**，然后单击**适配器**。  
  
     ![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4.  在**适配器属性**对话框框中，指定的名称为适配器并从**适配器**列表中，选择**WCF SAP**。  
  
     ![将 SAP 适配器添加到 BizTalk](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
[若要创建的 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)