---
title: "如何导出绑定到绑定文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3734ae6d-b790-40f2-8403-d7c7fdbe381b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 052f30e7e1fa2461d1332702dbd61b6aa76451b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bindings-to-a-binding-file"></a>如何导出绑定到绑定文件
你可以导出到使用绑定文件的另一个现有 BizTalk 应用程序的 BizTalk 应用程序的绑定。 你还可以导出组中的所有绑定或程序集的绑定。 随后，你可以导入的应用程序或组的这些绑定。  
  
 绑定文件是一个 XML 文件，描述 BizTalk 管理数据库和它们之间的关系中的项目。 它包含每个 BizTalk Server 业务流程、 管道、 映射或 BizTalk 程序集、 应用程序或组的作用域中的架构的绑定信息。 它包含每个发送端口的配置设置、 发送端口组、 接收端口、 接收位置，和方。 它还介绍每个业务流程绑定到的主机以及其信任级别。  
  
## <a name="why-to-export-to-a-binding-file"></a>为什么要将导出到绑定文件  
 绑定文件可以部署在下列情况中通过加速无需手动配置绑定：  
  
-   **将应用程序从一种部署环境移到另一个**  
  
     使用绑定文件可以通过避免需要手动配置绑定对于不同的部署环境，如从开发环境到测试环境的速度部署。  
  
-   **更新程序集**  
  
     绑定文件可用于自动将应用或重新应用到的程序集更新后的程序集绑定。  
  
-   **将程序集部署到多个 BizTalk 组**  
  
     你可以避免需要单独配置为使用绑定文件部署到多个 BizTalk 组程序集绑定。  
  
 使用绑定文件使您可以灵活地将绑定应用于应用程序。 如果导出为.msi 文件的应用程序，你仅可指定将.msi 文件导出的所有应用程序的绑定。 使用绑定文件可以执行以下操作：  
  
-   从当前应用程序的所有绑定、 从当前的组中，所有绑定或仅单个程序集的绑定将其导出到绑定文件。 （你执行操作，通过管理控制台中的应用程序中用于导出绑定命令。）  
  
-   以便立即应用自己的绑定或绑定会应用到另一组导入应用程序时，你可以将绑定文件添加到 （使用添加资源命令） 的应用程序。  
  
-   你可以将多个绑定文件添加到应用程序 （使用添加资源命令），并指定每个目标部署环境。 这使您要用于多个部署环境的一个部署包。 当你导入应用程序时，你可以选择要应用的绑定。  
  
-   可以将单独绑定文件导出为应用程序中的多个程序集。  
  
-   您可以在生成绑定文件后对其进行编辑，以更改其中的绑定信息。  
  
## <a name="how-to-export-to-a-binding-file"></a>如何将导出到绑定文件  
 通过执行导出绑定命令中的应用程序导出为绑定文件的应用程序的绑定[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]管理控制台中，或通过命令行上使用 BTSTask ExportBindings 命令。  
  
 出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。 在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。 您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。  
  
 绑定文件中的信息将取代现有的配置信息。 如果绑定文件中项目的名称与现有配置中项目的名称相匹配，则当您导入绑定文件时绑定文件中的项目将更新现有配置中的项目。  
  
 有关主机和信任级别绑定文件中的存储方式的信息，绑定文件中的主机和信任级别匹配主机和信任级别在应用程序和在其中应用绑定的顺序，请参阅[绑定文件和应用程序部署](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)。 有关如何导出 BizTalk 应用程序的绑定的说明，请参阅[如何导出 BizTalk 应用程序的绑定](http://go.microsoft.com/fwlink/?LinkId=155009)(http://go.microsoft.com/fwlink/?LinkId=155009)。