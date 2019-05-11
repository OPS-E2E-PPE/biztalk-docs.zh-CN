---
title: 导出 Bindings6 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- exporting, bindings
ms.assetid: 052a429e-3237-44d4-8933-00aa5edfb212
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcb3c26b684af381556a82684d94e9b13209dc75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345940"
---
# <a name="exporting-bindings"></a>导出绑定
在本部分中的主题介绍如何导出 BizTalk 组、 程序集或到.xml 文件的应用程序的绑定。 (绑定定义如何主机、 发送端口、 发送端口组、 接收端口、 接收位置，参与方是与业务流程、 管道、 映射和架构相关联。)你可以然后绑定导入从.xml 文件到另一个组或应用程序。 导入绑定将覆盖所有现有组或应用程序中具有相同名称的绑定。 此外可以将绑定添加到应用程序，不会覆盖现有绑定。 导入应用程序添加的绑定会生效。  
  
 您可能会发现，使用绑定文件加快了应用程序部署在以下情况下通过无需手动配置绑定：  
  
- 在一个部署环境之间移动应用程序。  
  
- 更新的程序集。  
  
- 将程序集以及及其绑定部署到多个 BizTalk 组。  
  
  有关用于这些目的使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
  有关导入和添加绑定的详细信息，请参阅[如何导入绑定到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)，[如何导入到 BizTalk 应用程序的绑定](../core/how-to-import-bindings-into-a-biztalk-application.md)，和[如何添加绑定向应用程序文件](../core/how-to-add-a-binding-file-to-an-application2.md)。  
  
> [!IMPORTANT]
>  绑定文件可能包含敏感数据。 请务必采取措施来保护文件。  
  
> [!NOTE]
>  出于安全原因，在导出绑定文件时 BizTalk Server 将从文件删除绑定密码。 导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。 发送端口在 BizTalk Server 管理控制台的传输属性对话框中配置密码，或接收位置。 有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何导出 BizTalk 组的绑定](../core/how-to-export-bindings-for-a-biztalk-group.md)  
  
-   [如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)  
  
-   [如何导出 BizTalk 程序集的绑定](../core/how-to-export-bindings-for-a-biztalk-assembly.md)  
  
-   [如何导出 EDI-AS2 解决方案的绑定](../core/how-to-export-bindings-for-an-edi-as2-solution.md)