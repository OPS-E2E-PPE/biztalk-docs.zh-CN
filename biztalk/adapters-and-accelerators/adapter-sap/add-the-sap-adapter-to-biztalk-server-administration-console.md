---
title: 将 SAP 适配器添加到 BizTalk Server 管理控制台 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95fc925d-0aac-4f0d-a19d-ad27469e4b3c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019edf01b4635777a91ac00efa0e2facebc7d1c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374271"
---
# <a name="add-the-sap-adapter-to-biztalk-server-administration-console"></a>将 SAP 适配器添加到 BizTalk Server 管理控制台
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以在 BizTalk 中可作为 WCF 自定义端口或 WCF SAP 端口使用。 如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF 自定义端口，您不需要添加到 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的默认情况下。 但是，如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF SAP 端口，必须首先添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 本主题说明了如何添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!IMPORTANT]
>  如果你想要配置 WCF 自定义端口，则不需要执行这些任务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="add-the-sap-adapter"></a>添加 SAP 适配器  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
3. 右键单击**适配器**，依次指向**新建**，然后单击**适配器**。  
  
    ![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. 在中**适配器属性**对话框框中，指定名称的适配器，从**适配器**列表中，选择**WCF SAP**。  
  
    ![将 SAP 适配器添加到 BizTalk](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")  
  
5. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)