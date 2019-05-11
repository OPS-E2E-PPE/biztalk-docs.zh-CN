---
title: 如何将绑定导出到绑定文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3734ae6d-b790-40f2-8403-d7c7fdbe381b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1a9868fab993578d5b62c0606a68ffce4b2d3fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253489"
---
# <a name="how-to-export-bindings-to-a-binding-file"></a>如何将绑定导出到绑定文件
您可以导出到使用的绑定文件的另一个现有 BizTalk 应用程序的 BizTalk 应用程序的绑定。 此外可以导出一个组中的所有绑定或程序集的绑定。 随后，您可以导入的应用程序或组的这些绑定。  
  
 绑定文件是一个 XML 文件，描述 BizTalk 管理数据库和它们之间的关系中的项目。 它包含每个 BizTalk Server 业务流程、 管道、 映射或架构的 BizTalk 程序集、 应用程序或组作用域中的绑定信息。 它包含每个发送端口的配置设置、 发送端口组、 接收端口、 接收位置，并参与方。 它还介绍了每个业务流程绑定到的主机和信任级别。  
  
## <a name="why-to-export-to-a-binding-file"></a>为何要将导出到绑定文件  
 绑定文件可以加速部署在以下情况下通过无需手动配置绑定：  
  
- **在一个部署环境之间移动应用程序**  
  
   使用绑定文件可以通过无需手动配置绑定对于不同的部署环境，如从开发环境到测试环境的速度部署。  
  
- **更新的程序集**  
  
   绑定文件可用于自动应用或重新应用到的程序集的更新后的程序集的绑定。  
  
- **将程序集部署到多个 BizTalk 组**  
  
   你可以无需单独配置使用绑定文件部署到多个 BizTalk 组的程序集的绑定。  
  
  使用绑定文件使您可以灵活地将绑定应用到应用程序。 导出到.msi 文件的应用程序时，您可以只指定，所有应用程序的绑定将导出到.msi 文件。 使用绑定文件可以执行以下操作：  
  
- 当前应用程序中的所有绑定、 当前组中的所有绑定或仅单个程序集的绑定将其导出到绑定文件。 （仍使用此管理控制台中为应用程序中使用导出绑定命令。）  
  
- 可以向应用程序 （使用添加资源命令） 添加绑定文件，以便立即应用其绑定或使应用程序导入到另一个组时应用绑定。  
  
- 可以将多个绑定文件添加到应用程序 （使用添加资源命令），并指定每个目标部署环境。 这使您要用于多个部署环境的单个部署包。 导入应用程序时，可以选择要应用的绑定。  
  
- 您可以单独的绑定文件导出的应用程序中的多个程序集。  
  
- 生成对其进行更改其绑定信息后，可以编辑绑定文件。  
  
## <a name="how-to-export-to-a-binding-file"></a>如何将导出到绑定文件  
 通过在 BizTalk Server 管理控制台中，执行应用程序的导出绑定命令或通过在命令行上使用 BTSTask ExportBindings 命令导出到绑定文件的应用程序的绑定。  
  
 出于安全原因，在导出绑定文件时 BizTalk Server 将从文件删除绑定密码。 导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。 发送端口在 BizTalk Server 管理控制台的传输属性对话框中配置密码，或接收位置。  
  
 绑定文件中的信息将取代现有的配置信息。 如果绑定文件中项目的名称与现有配置中的项目的名称相匹配，绑定文件中的项目的项目将更新现有配置中导入绑定文件时。  
  
 有关如何将主机和信任级别存储在绑定文件的内容，如何将绑定文件中的主机和信任级别匹配的主机和信任级别中应用程序，以及应用绑定的顺序，请参阅[绑定文件和应用程序部署](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)。 有关如何导出 BizTalk 应用程序的绑定的说明，请参阅[如何导出 BizTalk 应用程序的绑定](http://go.microsoft.com/fwlink/?LinkId=155009)(http://go.microsoft.com/fwlink/?LinkId=155009)。