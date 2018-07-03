---
title: 将 SQL 适配器添加到 BizTalk Server 管理控制台 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd974f28-c9cb-46de-95be-83716231ebcd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff3eb1aa8870316ec506a61658c34db6acc7f62c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005726"
---
# <a name="adding-the-sql-adapter-to-biztalk-server-administration-console"></a>将 SQL 适配器添加到 BizTalk Server 管理控制台
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以在 BizTalk 中可作为 WCF 自定义端口或 WCF SQL 端口使用。 如果你想要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过 WCF 自定义端口，您不需要添加到 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的默认情况下。 但是，如果你想要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过 WCF SQL 端口，必须首先添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 本主题说明如何将添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!IMPORTANT]
>  不需要执行以下步骤，如果你想要配置 WCF 自定义端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="add-the-sql-adapter"></a>添加 SQL 适配器  
  
1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 展开**BizTalk 组**，展开**平台设置**，然后选择**适配器**。  
  
3. 右键单击**适配器**，依次指向**新建**，然后选择**适配器**。  
  
    ![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. 在中**适配器属性**对话框框中，输入的名称对于适配器，然后从**适配器**列表中，选择**WCF-SQL**。  
  
    ![添加 WCF&#45;SQL 适配器添加到 BizTalk](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")  
  
5. 选择“确定”。  
  
## <a name="see-also"></a>请参阅  
 [若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)