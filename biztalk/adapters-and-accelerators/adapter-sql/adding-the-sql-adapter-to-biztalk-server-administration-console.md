---
title: "将 SQL 适配器添加到 BizTalk Server 管理控制台 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd974f28-c9cb-46de-95be-83716231ebcd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3510fb31bffe4c5823593fac34d5d5f1d5849c65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-the-sql-adapter-to-biztalk-server-administration-console"></a>将 SQL 适配器添加到 BizTalk Server 管理控制台
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可在 BizTalk 作为 WCF 自定义端口或 WCF SQL 端口。 如果你想要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过 WCF 自定义端口，你不需要添加到的 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]默认情况下的管理控制台。 但是，如果你想要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过 WCF SQL 端口，您必须首先添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 本主题说明如何将添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!IMPORTANT]
>  不需要按照这些步骤操作，如果你想要配置的 WCF 自定义端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="add-the-sql-adapter"></a>添加 SQL 适配器  
  
1.  打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  展开**BizTalk 组**，展开**平台设置**，然后选择**适配器**。  
  
3.  右键单击**适配器**，指向**新建**，然后选择**适配器**。  
  
     ![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4.  在**适配器属性**对话框框中，为使适配器，以及从输入名称**适配器**列表中，选择**WCF SQL**。  
  
     ![添加 WCF &#45;到 BizTalk SQL 适配器](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")  
  
5.  选择“确定”。  
  
## <a name="see-also"></a>另请参阅  
 [开发具有 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)