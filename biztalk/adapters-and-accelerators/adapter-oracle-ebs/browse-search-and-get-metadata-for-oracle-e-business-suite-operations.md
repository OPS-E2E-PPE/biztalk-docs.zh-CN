---
title: 浏览、 搜索和用于 Oracle E-business Suite 操作获取元数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05a0656c-84d0-4f25-9571-90a9df587b8c
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a26b13ddef6efe9214e7d889d5d8e02d2f1505cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217789"
---
# <a name="browse-search-and-get-metadata-for-oracle-e-business-suite-operations"></a>浏览、 搜索和用于 Oracle E-business Suite 操作获取元数据
本部分提供有关如何使用信息[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]和[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 通过使用这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件，你可以：  
  
-   浏览的操作以检索元数据。  
  
-   搜索操作以检索元数据。  
  
-   添加所选操作的消息架构和端口绑定配置文件添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目时使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
-   WCF 客户端类或所选的操作和配置文件 (app.config) 的 WCF 服务协定 （接口） 向项目中添加非 BizTalk 编程时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
## <a name="how-is-the-metadata-categorized"></a>是如何的元数据分类？  
 [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]提供三个不同的视图中，连接到 Oracle E-business Suite server 中提供的项目的-**基于应用程序的视图**，**基于项目的视图**，和**基于架构的视图**。 为什么需要三个不同的视图项目在同一组？ 下表列出的原因，您应为何使用特定的视图。  
  
|视图|何时使用它|  
|----------|------------------------|  
|**基于应用程序的视图**|Oracle E-business Suite 应用程序名称的情况下，此视图进行分类。 当你知道哪个应用程序包含你想要使用的项目时，请使用此视图。|  
|**基于项目的视图**|此视图的 Oracle E-business Suite 项目进行分类。 当你知道要使用的工作，但你的 Oracle E-business Suite 项目不能确定项目属于哪个应用程序时，请使用此视图。 使用此视图，你可以搜索特定项目在所有 Oracle E-business Suite 应用程序。<br /><br /> 基于项目的视图还列出如 PL SQL Api、 表、 视图、 函数和过程的基础 Oracle 数据库中的项目。 这些项目进行进一步分类基于它们所属的架构。 因此，基于项目的另一个用途是视图的使用属于您的架构的项目以及属于其他架构的项目。 此视图还可在所有架构中搜索项目。|  
|**基于架构的视图**|此视图进行分类的基础的 Oracle 数据库中可用的架构。 当你知道的架构具有你想要使用的项目时，请使用此视图。 在此视图中，如归类为 PL SQL Api、 过程、 函数、 表和视图的项目。|  
  
 有关 Oracle E-business Suite 项目分类的方式的详细信息，请参阅[连接到 Visual Studio 使用添加适配器元数据向导中的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md)另一个组织中的项目的关键原因不同的视图是方便要搜索特定项目。 有关如何搜索项目的详细信息，请参阅[用于 Oracle E-business Suite 操作的搜索](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md)。  
  
> [!IMPORTANT]
>  节点显示根据连接建立连接时指定的 URI。 如果你指定的 Oracle E-business Suite 项目不具有权限的凭据，则无法使用中的项目**基于应用程序的视图**。 此外，**基于项目的视图**不会列出属于 Oracle E-business Suite 的项目。  
  

  
## <a name="see-also"></a>另请参阅  
 [获取 Visual Studio 中的 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)