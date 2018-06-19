---
title: 适配器组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 383e8bcb-2b4d-40f9-9e98-f49e8d6f30f7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2a5f2a78a9ea555d22f585c0aa50eda65b6c287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225325"
---
# <a name="adapter-components"></a>适配器组件
自定义适配器共享本地适配器所使用的标准配置、管理和设置机制。 为适配器框架标准化，自定义适配器通过使用进行管理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 下图显示的自定义适配器的主要组件： 适配器注册表文件、 适配器设计时组件和适配器运行时组件。  
  
 ![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")  
  
## <a name="adapter-registry-file"></a>适配器注册表文件  
 有关适配器的特定信息必须在注册表和 BizTalk 管理数据库中注册。 适配器别名、接收处理程序、接收位置和传输类型之类的信息被称为元数据。 这些元数据项创建在过程中手动适配器注册使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 或者，你可以运行适配器注册表向导 (AdapterRegistryWizard.exe) SDK 实用程序生成自定义适配器注册表文件。 双击此注册表文件，或单击**导入**上**文件**使用注册表编辑器 (regedit32.exe) 的菜单将元数据写入到注册表。  
  
> [!NOTE]
>  运行此注册表文件并不能将适配器信息添加到 BizTalk 管理数据库中。 你必须手动执行此操作通过使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="design-time-component"></a>设计时组件  
 自定义适配器的用户界面 (UI) 通过使用适配器框架来实现。 这是一种高效的 UI 开发方法，因为 UI 可以通过作为适配器程序集一部分提供的 XML 架构来呈现。 只需少量代码就可以将架构内容转换为 UI，以配置适配器属性。  
  
 对于需要与 SQL 适配器之类的应用程序适配器通信的业务流程，可以使用“添加适配器元数据”向导向某个 BizTalk 项目添加适配器元数据，如架构、消息类型和端口类型。 将“添加适配器元数据”向导与应用程序适配器一同使用可以将相应架构拖入系统。 若要调用此向导从在 BizTalk （非适配器） 项目内的，右键单击项目，指向**添加生成的项**，单击**添加适配器元数据**然后从列表中选择注册适配器元数据导入的适配器。  
  
## <a name="run-time-component"></a>运行时组件  
 适配器通常包括两个公共运行时组件： 实现消息接收方，并实现消息发送方的组件的组件。 这些组件可以部署在同一程序集内，也可以部署在两个不同的程序集内。  
  
#### <a name="receive-adapter"></a>接收适配器  
 接收适配器负责通过将网络/数据源流附加到消息正文来创建新的 BizTalk 消息。 它还添加与接收数据的终结点相关的任何元数据，然后将该消息提交给消息引擎。 适配器从接收终结点中删除数据，或将相应的确认消息发送到客户端，该值指示数据已接受到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
#### <a name="send-adapter"></a>发送适配器  
 发送适配器负责使用其特定的传输协议将 BizTalk 消息发送到指定的终结点。  
  
## <a name="see-also"></a>另请参阅  
 [什么是适配器 Framework？](../core/what-is-the-adapter-framework.md)