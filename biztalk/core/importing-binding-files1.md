---
title: "导入绑定 Files1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- CLASSPATH environment variable
- importing binding files
- cleaning target computer
ms.assetid: b2a9b19b-2d3d-45ea-bd92-a2501791b86a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fca64580b692f01834b48085aa2d88085fb743
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a>导入绑定文件
在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导入绑定文件之前，请验证以下各项：  
  
-   CLASSPATH 指向 PeopleSoft 特定文件的特定位置。 验证这些文件的位置是否在新计算机上相同，或编辑绑定文件。  
  
-   响应的文件夹必须存在并且可在新计算机上完全相同，或编辑绑定文件。  
  
-   如果在配置中存在 PeopleSoft Enterprise 系统密码，则在绑定文件中另存为 *****。 有关详细信息，请参阅[部署限制](../core/deployment-limitations3.md)。  
  
> [!NOTE]
>  部署会覆盖接收位置配置。 如果在目标计算机上部署绑定文件和程序集，则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。  
  
 有关导入绑定文件的分步指导信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的主题“如何将绑定导入到 BizTalk 组”。  
  
## <a name="cleaning-the-target-computer"></a>清理目标计算机  
 按照以下步骤执行操作可清理目标计算机，从而部署新的应用程序。  
  
#### <a name="to-clean-the-target-computer"></a>若要清除目标计算机中的  
  
-   删除发送端口和接收位置绑定到业务流程。  
  
     如果没有在目标计算机上安装 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，则可通过运行下面的脚本删除端口：  
  
     **\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove 发送 Port\VBScript\RemoveSendPort.vbs**  
  
     **\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove 接收 Port\VBScript\RemoveReceivePort.vbs**  
  
     例如，在命令提示符下运行：  
  
     **cscript RemoveSendPort.vbs\<发送端口名称 >**  
  
## <a name="see-also"></a>另请参阅  
 [部署端口和程序集](../core/deploying-ports-and-assemblies5.md)