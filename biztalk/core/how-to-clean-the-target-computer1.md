---
title: "如何清洗目标 Computer1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, removing
- send ports, removing
- cleaning target computer
ms.assetid: 78986a33-3c77-48dc-88c4-b78f52911c22
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7adf1761b6eb31ce158232c22af457b9c716a812
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-clean-the-target-computer"></a>如何清洗目标计算机
部署将覆盖接收位置配置。 当你部署的目标计算机上，发送端口的绑定文件 （和程序集） 和接收位置已替换为 XML 绑定文件中导入时。  
  
### <a name="to-clean-the-target-computer"></a>若要清除目标计算机中的  
  
-   删除发送端口和接收位置绑定到业务流程。  
  
     如果你没有在目标计算机上安装的 Microsoft Visual Studio，你可以通过运行这些脚本中删除的端口：  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
         例如，在命令提示符下运行：  
  
         **cscript RemoveSendPort.vbs\<发送端口名称 >**  
  
## <a name="see-also"></a>另请参阅  
 [部署端口和程序集](../core/deploying-ports-and-assemblies1.md)