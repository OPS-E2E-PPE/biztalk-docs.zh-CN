---
title: BizTalk Server 如何实例化适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ebe7585-5939-4142-9281-990b4849e28d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32e6e40bf39c09e747391bba51a54143fc67e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246693"
---
# <a name="how-biztalk-server-instantiates-an-adapter"></a>BizTalk Server 如何实例化适配器
在 BizTalk 服务启动时，所有接收适配器都将被实例化，只要它们具有一个或多个已配置且处于活动状态的接收位置。 默认情况下，在消息引擎从队列中删除要通过使用某一发送适配器发送的第一个消息前，将不会实例化该发送适配器。 （这有时称为"延迟创建。）但是，如果你需要实例化服务启动后上的发送适配器，你可以使用**InitTransmitterOnServiceStart**适配器功能。 这将引导消息引擎在服务启动时创建发送适配器，而非使用默认的“懒创建”方法。 默认的“懒创建”方法有助于减少在终结点上未配置适配器时占用的系统资源量。  
  
 在创建自定义适配器时，建议使用托管代码。 但是，可以使用本地 COM 组件。 对于 COM 组件，该适配器在正常的方式使用中实例化**CoCreateInstance**。  
  
 对于托管代码中，你需要指定.NET**类型**在配置文件中; 中的程序集路径是可选的。  
  
 下面介绍可行的部署选项：  
  
|.NET 类型|程序集路径|程序集部署方法|  
|---------------|-------------------|--------------------------------|  
|Specified|未指定|通过 XCopy 复制方式将程序集复制到产品目录或者产品目录中的子目录，其名称与该程序集同名|  
|Specified|未指定|全局程序集缓存 (GAC) 程序集|  
|Specified|Specified|将程序集以 XCopy 方式复制到指定目录|  
  
 **故障排除提示：** 当你创建使用托管的代码中，如果无法创建适配器时，使用 fuslogvw.exe 工具来确定是否存在无法解析的程序集的引用。 这是一个常见错误。  
  
 下图显示根据指定的配置创建适配器的逻辑：  
  
 ![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")  
  
 下表提供了一个示例，介绍如何配置接收适配器以及配置运行时程序集的方式。  
  
|程序集部署方法|InboundTypeName|InboundAssemblyPath|  
|--------------------------------|---------------------|-------------------------|  
|指定程序集位置|Microsoft.Samples.MyReceiveAdapter|C:\MyAdapter\MyAdapter.dll|  
|指定 .NET 类型（包括公钥、版本和区域性信息）|Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020|N/A|  
|GAC 程序集|Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020|N/A|