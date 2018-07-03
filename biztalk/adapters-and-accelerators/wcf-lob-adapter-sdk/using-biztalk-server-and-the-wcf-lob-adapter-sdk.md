---
title: 使用 BizTalk Server 和 WCF LOB 适配器 SDK |Microsoft Docs
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
ms.openlocfilehash: 46b06f832fd9ff36f0e274c1599b577bc9ec6010
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989974"
---
# <a name="using-biztalk-server-and-the-wcf-lob-adapter-sdk"></a>使用 BizTalk Server 和 WCF LOB 适配器 SDK
本部分包含的关系的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 在本部分中包含的信息包括两个不同的框架提供的每个比较和迁移提示[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]自定义适配器。  

## <a name="relationship-with-the-sdk-and-biztalk-server"></a>使用 SDK 和 BizTalk Server 的关系
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 提供了一个 SDK 和工具和组件，使开发人员能够编写复杂的业务线系统包含一组动态的操作和数据适配器的集合。 适配器公开为 WCF 自定义绑定中，这种情况下可以使用的应用程序可以使用 WCF 绑定。  

 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 是一个产品，使消息流和协调一组不同的企业系统;之间的通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和外部系统将通过适配器采用外部消息并将其转换为的格式适用于处理由处理[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  

 在这两种技术相交[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]WCF 适配器。 它可使用公开的 WCF 绑定，并因此占用操作和由适配器编写的公开数据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  

 以下各图提供了如何在使用 BizTalk WCF 适配器和 WCF LOB 适配器的高级概述[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]与目标 LOB 系统进行通信。  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8dd622c6-ab5e-4cd9-aa86-5176f5c62203.gif "8dd622c6-ab5e-4cd9-aa86-5176f5c62203")  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4f503084-da4f-41cb-92b9-eaea25d1b456.gif "4f503084-da4f-41cb-92b9-eaea25d1b456")  

## <a name="differences-between-the-sdk-and-the-biztalk-server-adapter-framework"></a>SDK 和 BizTalk Server 适配器框架之间的差异

虽然两个[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]适配器框架用于编写自定义适配器提供的 SDK、 那里是支持量方面的重大差异提供 API 的方面和工具，并且还在可重复使用的适配器一次它是已完成。  

 下表总结了一些这两个框架之间的主要区别。  


|     功能      |                                                                   [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]                                                                   |                  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 适配器框架                   |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|       API        | [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] 和[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]程序集，提供用于处理、 连接管理和消息传送的元数据的帮助类 |                                            COM 中，为适配器操作提供基本支持。                                             |
| 适配器公开 |                                                            公开为 WCF 绑定;适用于任何应用程序都可以使用 WCF 绑定。                                                             | 只能与公开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]; 不可重用由其他应用程序。 |
|      工具       |                       [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]用于元数据浏览器 [!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)]                       |                                                                    不适用                                                                     |
|  扩展性   |                                                                                       是 （作为 WCF 通道扩展）                                                                                        |                                                                     “否”                                                                     |

 使用 BizTalk 适配器框架创建的适配器是通过仅在 BizTalk Server 内使用。 另一方面，适配器写入到[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]作为自定义 WCF 绑定。 这拓宽了其市场的任何应用程序需要使用的服务，这实际上是任何.NET 应用程序包括[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 在使用基于 WCF 的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用 BizTalk WCF 适配器，并继续在本地的 BizTalk 适配器的同时存在。 

