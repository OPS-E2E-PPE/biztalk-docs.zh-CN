---
title: 使用 BizTalk Server 和 WCF LOB 适配器 SDK |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43ff0357-76e6-42bc-a1f7-0385d9378a5f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41fffdf81d6e5565f9799594ddee485be485fed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226013"
---
# <a name="using-biztalk-server-and-the-wcf-lob-adapter-sdk"></a>使用 BizTalk Server 和 WCF LOB 适配器 SDK
本部分包含有关的关系的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 本节中所包含的信息包括的每个提供的两个不同框架的比较和迁移提示[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]自定义适配器。  
  
## <a name="relationship-with-the-sdk-and-biztalk-server"></a>使用 SDK 和 BizTalk Server 的关系
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了一个 SDK 和工具和组件，使开发人员编写复杂的业务线系统包含一组动态的操作和数据适配器的集合。 适配器公开为 WCF 自定义绑定，这种情况下可以由应用程序可以使用 WCF 绑定。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]是一种产品，可支持消息流和一组不同的企业系统; 之间的协作之间的通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和外部系统处理通过适配器可采用外部消息并将其转换为的格式以供处理适合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 这两种技术相交在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]WCF 适配器。 它可以使用由 WCF 公开的绑定，并因此使用的操作和数据适配器用编写公开[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  
  
 以下各图概述了如何在使用的 BizTalk WCF 适配器和 WCF LOB 适配器的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]与目标 LOB 系统进行通信。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8dd622c6-ab5e-4cd9-aa86-5176f5c62203.gif "8dd622c6-ab5e-4cd9-aa86-5176f5c62203")  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4f503084-da4f-41cb-92b9-eaea25d1b456.gif "4f503084-da4f-41cb-92b9-eaea25d1b456")  

## <a name="differences-between-the-sdk-and-the-biztalk-server-adapter-framework"></a>SDK 与 BizTalk Server 适配器框架之间的差异

虽然两个[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]适配器框架为编写自定义适配器提供 SDK，存在都支持量方面的重大差异提供在 API 的方面，工具，还在可重用性的适配器一次很已完成。  
  
 下表总结了一些之间的两个框架的主要差异。  
  
|功能|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]适配器框架|  
|---|---|---|  
|API|[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]和[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]程序集，提供用于元数据处理、 连接管理、 和消息传送帮助类|COM，来完成适配器操作提供基本支持。|  
|适配器公开|公开为 WCF 绑定;可用的任何应用程序可以使用 WCF 绑定。|仅为公开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]; 不可重用由其他应用程序。|  
|工具|[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]用于元数据浏览器[!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)]|不适用|  
|扩展性|是 （作为 WCF 通道扩展）|是|  
  
 使用 BizTalk 适配器框架创建的适配器是可以从仅在 BizTalk Server。 另一方面，写入到的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]作为自定义 WCF 绑定。 此扩展其应用范围的任何应用程序使用一个服务，它所有的实用的角度而言是任意.NET 应用程序包括[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 在中使用的基于 WCF 的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用 BizTalk WCF 适配器和继续存在于与本机 BizTalk 适配器并行。 
 
