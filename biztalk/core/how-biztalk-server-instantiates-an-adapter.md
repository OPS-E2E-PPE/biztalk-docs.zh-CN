---
title: BizTalk Server 如何实例化适配器 |Microsoft Docs
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
ms.openlocfilehash: 4082d9ac17ce7e97b94cd9b585eb1a6ce326f0e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344227"
---
# <a name="how-biztalk-server-instantiates-an-adapter"></a>BizTalk Server 如何实例化适配器
BizTalk 服务启动时，所有接收适配器进行实例化，只要它们具有一个或多个已配置且处于活动状态的接收位置。 默认情况下，直到要通过使用发送的第一个消息从队列删除消息引擎不实例化发送适配器的发送适配器。 （这有时称为"懒创建。）但是，如果需要实例化发送适配器在服务启动，则可以使用**InitTransmitterOnServiceStart**适配器功能。 这会指示消息引擎在服务启动，而不是使用默认延迟创建创建发送适配器。 默认的懒创建方法有助于减少终结点上未配置适配器时使用的系统资源的数量。  
  
 创建自定义适配器时，我们建议使用托管的代码。 但是，就可以使用本机 COM 组件。 对于 COM 组件实例化适配器中采用正常方式使用**CoCreateInstance**。  
  
 对于托管代码中，您需要指定.NET**类型**配置文件中; 中的程序集路径是可选的。  
  
 可能的部署选项包括：  
  
|.NET 类型|程序集路径|程序集部署方法|  
|---------------|-------------------|--------------------------------|  
|Specified|未指定|与程序集 XCopy 到产品目录或者具有相同名称的产品目录中子目录的程序集|  
|Specified|未指定|全局程序集缓存 (GAC) 程序集|  
|Specified|Specified|XCopy 到指定的目录的程序集|  
  
 **故障排除提示：** 创建使用托管的代码中，如果在无法创建适配器时，使用 fuslogvw.exe 工具确定是否存在无法解析的程序集的引用。 这是一个常见的错误。  
  
 下图显示了用于创建适配器，具体取决于指定的配置的逻辑：  
  
 ![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")  
  
 下表提供了示例的接收适配器可能配置方式，并可能配置的运行时程序集的方法。  
  
|程序集部署方法|InboundTypeName|InboundAssemblyPath|  
|--------------------------------|---------------------|-------------------------|  
|指定程序集位置|Microsoft.Samples.MyReceiveAdapter|C:\MyAdapter\MyAdapter.dll|  
|指定.NET 类型 （包括公钥、 版本和区域性信息）|Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020|不可用|  
|GAC 程序集|Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020|不可用|