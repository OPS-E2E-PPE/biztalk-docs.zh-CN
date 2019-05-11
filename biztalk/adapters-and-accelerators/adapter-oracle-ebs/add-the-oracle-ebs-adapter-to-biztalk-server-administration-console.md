---
title: 将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台 |Microsoft Docs
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
ms.openlocfilehash: b11a6959ecffb7447c577153104977bd90815105
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375815"
---
# <a name="add-the-oracle-e-business-suite-adapter-to-biztalk-server-administration-console"></a>将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可作为 WCF 自定义端口或 WCF OracleEBS 端口在 BizTalk Server 中使用。 如果你想要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过 WCF 自定义端口，您不需要添加到 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的默认情况下。 但是，如果你想要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过 WCF OracleEBS 端口，必须首先添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 本主题说明了如何将 WCF OracleEBS 适配器添加到添加[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!IMPORTANT]
>  如果你想要配置的 WCF 自定义端口[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，则不需要执行此过程。  
  
### <a name="to-add-the-oracle-e-business-suite-adapter"></a>若要添加 Oracle E-business Suite 适配器  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
3. 右键单击**适配器**，依次指向**新建**，然后单击**适配器**。  
  
    ![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. 在中**适配器属性**对话框框中，指定名称的适配器，从**适配器**列表中，选择**Wcf-oracleebs**。  
  
    ![添加 WCF&#45;OracleEBS 适配器添加到 BizTalk](../../adapters-and-accelerators/adapter-oracle-ebs/media/3e2cde5a-9f32-489c-a931-0dd509451e62.gif "3e2cde5a-9f32-489c-a931-0dd509451e62")  
  
5. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [若要创建 Oracle E-business Suite 的应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)