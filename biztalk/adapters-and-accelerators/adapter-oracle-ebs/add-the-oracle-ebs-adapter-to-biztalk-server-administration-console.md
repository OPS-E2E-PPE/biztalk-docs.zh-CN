---
title: 将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b126aa-2a05-49fa-80e1-f1d5c21ad60f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 492a99d8835990ee630dfb0ad0603279873eca4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216525"
---
# <a name="add-the-oracle-e-business-suite-adapter-to-biztalk-server-administration-console"></a>将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可以作为 WCF 自定义端口或 WCF OracleEBS 端口在 BizTalk Server 中使用。 如果你想要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过 WCF 自定义端口，你不需要添加到的 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]默认情况下的管理控制台。 但是，如果你想要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过 WCF OracleEBS 端口，您必须首先添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 本主题将说明了如何将添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!IMPORTANT]
>  如果你想要配置的 WCF 自定义端口[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，无需执行此过程。  
  
### <a name="to-add-the-oracle-e-business-suite-adapter"></a>若要添加 Oracle E-business Suite 适配器  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
3.  右键单击**适配器**，指向**新建**，然后单击**适配器**。  
  
     ![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4.  在**适配器属性**对话框框中，指定的名称为适配器并从**适配器**列表中，选择**WCF OracleEBS**。  
  
     ![WCF &#45; 添加到 BizTalk OracleEBS 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/media/3e2cde5a-9f32-489c-a931-0dd509451e62.gif "3e2cde5a-9f32-489c-a931-0dd509451e62")  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)