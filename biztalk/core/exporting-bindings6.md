---
title: "导出 Bindings6 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- exporting, bindings
ms.assetid: 052a429e-3237-44d4-8933-00aa5edfb212
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3362984eca1dcec4fb68bfbac92c30da81de8a3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exporting-bindings"></a>导出绑定
本部分中的主题介绍如何导出 BizTalk 组、 程序集，或到一个.xml 文件的应用程序的绑定。 (绑定定义主机，发送端口将端口组的发送、 接收端口，则接收位置，各方都与业务流程、 管道、 映射和架构相关联。)您然后可以从.xml 文件到另一个组或应用程序来导入绑定。 导入绑定将覆盖任何现有组或应用程序中的相同名称的绑定。 你还可以向应用程序，不会覆盖现有绑定添加绑定。 在导入应用程序之前，你添加的绑定不会生效。  
  
 你可能会发现，使用绑定文件加快了应用程序部署在下列情况中通过避免需要手动配置绑定：  
  
-   将应用程序从一种部署环境移到另一个。  
  
-   更新程序集。  
  
-   将其绑定以及程序集部署到多个 BizTalk 组。  
  
 有关针对这些目的使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
 有关导入和添加绑定的详细信息，请参阅[如何导入绑定到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)，[如何导入绑定到 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)，和[如何将绑定添加向应用程序的文件](../core/how-to-add-a-binding-file-to-an-application2.md)。  
  
> [!IMPORTANT]
>  绑定文件可能包含敏感数据。 请确保采取措施来保护文件。  
  
> [!NOTE]
>  出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。 在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。 您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。 有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何导出绑定 BizTalk 组](../core/how-to-export-bindings-for-a-biztalk-group.md)  
  
-   [如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)  
  
-   [如何导出 BizTalk 程序集绑定](../core/how-to-export-bindings-for-a-biztalk-assembly.md)  
  
-   [如何导出 EDI AS2 解决方案的绑定](../core/how-to-export-bindings-for-an-edi-as2-solution.md)