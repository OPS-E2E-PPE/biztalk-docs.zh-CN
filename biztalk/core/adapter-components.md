---
title: 适配器组件 |Microsoft Docs
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
ms.openlocfilehash: 215bb12537bbd0df859c59c8914c6cba63cd139a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361603"
---
# <a name="adapter-components"></a>适配器组件
自定义适配器共享标准化的配置、 管理和使用的本地适配器的安装程序机制。 自定义适配器通过使用适配器框架进行标准化，来管理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 下图显示了自定义适配器的主要组件： 适配器注册表文件、 适配器设计时组件和适配器运行时组件。  
  
 ![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")  
  
## <a name="adapter-registry-file"></a>适配器注册表文件  
 必须在注册表和 BizTalk 管理数据库中注册适配器有关的特定信息。 信息的适配器的别名，如接收处理程序、 接收位置和传输类型被称为元数据。 在手动适配器使用注册期间创建这些元数据条目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 或者，可以运行适配器注册向导 (AdapterRegistryWizard.exe) SDK 实用工具生成自定义适配器的注册表文件。 双击此注册表文件，或单击**导入**上**文件**使用注册表编辑器 (regedit32.exe) 的菜单将元数据写入到注册表。  
  
> [!NOTE]
>  运行此注册表文件不会添加到 BizTalk 管理数据库适配器信息。 通过使用，必须手动执行此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="design-time-component"></a>设计时组件  
 通过使用适配器框架实现自定义适配器的用户界面 (UI)。 这是因为从 XML 架构作为适配器的程序集的一部分提供呈现的 UI 的 UI 开发高效方法。 少量的代码需要的架构内容转换为 UI，以配置适配器的属性。  
  
 为业务流程，无需与 SQL 适配器之类的应用程序适配器进行通信，添加适配器元数据向导，可向 BizTalk 项目添加适配器元数据，例如架构、 消息类型和端口类型。 添加适配器元数据向导应用程序适配器使用相应架构拖入系统。 若要调用此向导从 BizTalk （非适配器） 项目中的，右键单击项目，指向**添加生成的项**，单击**添加适配器元数据**然后从列表中选择注册若要导入适配器元数据的适配器。  
  
## <a name="run-time-component"></a>运行时组件  
 适配器通常包含两个公共运行时组件： 实现消息接收方和实现消息发件人的组件的组件。 在同一程序集中或两个不同的程序集，这些组件可以进行部署。  
  
#### <a name="receive-adapter"></a>接收适配器  
 接收适配器负责通过将网络/数据源流附加到消息正文中创建新的 BizTalk 消息。 它还会添加到终结点的数据接收的然后该将消息提交到消息引擎相关的任何元数据。 适配器从接收终结点删除数据，或将相应的确认消息发送到客户端，该值指示数据已被接受到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
#### <a name="send-adapter"></a>发送适配器  
 发送适配器负责将 BizTalk 消息发送到指定的终结点使用其特定的传输协议。  
  
## <a name="see-also"></a>请参阅  
 [适配器框架概述](../core/what-is-the-adapter-framework.md)