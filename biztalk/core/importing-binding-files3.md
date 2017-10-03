---
title: "导入绑定 Files3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- target computer, cleaning
- importing binding files
- cleaning target computer
ms.assetid: 955bb3e1-3dbc-43ce-9126-205d838ae662
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa1d95c40e3e556068e15a269ee4cbb7e995429a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a>导入绑定文件
BizTalk Server 用于导入绑定文件之前，请验证以下各项：  
  
-   CLASSPATH 指向 JD Edwards 特定文件的特定位置。 验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。  
  
-   用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。  
  
-   如果在配置中存在 JD Edwards 系统密码，则在绑定文件中另存为 *****。 有关详细信息，请参阅[部署限制](../core/deployment-limitations2.md)。  
  
> [!NOTE]
>  部署将覆盖接收位置配置。 如果在目标计算机上部署绑定文件（和程序集），则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。  
  
## <a name="importing-the-binding-files"></a>导入绑定文件  
 使用以下过程导入绑定文件。  
  
#### <a name="to-import-the-binding-files"></a>导入绑定文件  
  
1.  上**启动**菜单上，指向**Program Files**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**若要启动 BizTalk Server 管理控制台。  
  
2.  展开 BizTalk Server 管理中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  右键单击所需应用程序，指向**导入**，然后单击**绑定**。  
  
4.  在**导入绑定**对话框中，浏览并选择绑定文件，然后单击**打开**。  
  
## <a name="cleaning-the-target-computer"></a>清理目标计算机  
 使用以下过程清理目标计算机。  
  
#### <a name="to-clean-the-target-computer"></a>若要清除目标计算机中的  
  
-   删除发送端口和绑定到业务流程的接收位置。  
  
## <a name="see-also"></a>另请参阅  
 [创建博士 Edwards OneWorld 发送处理程序](../core/creating-jd-edwards-oneworld-send-handlers.md)   
 [部署端口和程序集](../core/deploying-ports-and-assemblies4.md)