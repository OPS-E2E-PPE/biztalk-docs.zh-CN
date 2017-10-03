---
title: "导入绑定 Files2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- assemblies, removing from database
- importing binding files
- target computers, cleaning
- BizTalk assemblies, removing from database
ms.assetid: 9e552a4b-06ec-4887-b17b-a625c137699f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3783b21385c210c454bcd3d4c951f2200a6ec866
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a>导入绑定文件
本主题提供有关导入过程，为博士 Edwards EnterpriseOne 部署的 BizTalk Adapter 时的一些信息。 当你重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置已替换为 XML 绑定文件中时它们重新导入。  
  
### <a name="to-clean-the-target-computer"></a>若要清除目标计算机中的  
  
-   删除发送端口和接收位置绑定到业务流程。  
  
     如果未安装目标计算机上安装的 Visual Studio，你可以通过运行脚本中删除的端口：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
     删除发送 Port\VBScript\RemoveSendPort.vbs  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
     删除接收 Port\VBScript\RemoveReceivePort.vbs  
  
     例如，从命令提示符下运行：  
  
     **cscript RemoveSendPort.vbs\<发送端口名称 >**  
  
## <a name="see-also"></a>另请参阅  
 [部署端口和程序集](../core/deploying-ports-and-assemblies3.md)