---
title: ListTypes 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94febe8a-4c1e-4581-a6d1-ef579633e745
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda39d682bfb4649fc22afd892dd13849bfd1b09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380720"
---
# <a name="listtypes-command"></a>ListTypes 命令
列出可以添加到项目类型的所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用**AddResource**命令。 有关详细信息**AddResource**命令，请参阅[AddResource 命令](../core/addresource-command.md)。  
  
 受支持的项目类型的完全限定的名称如下所示：  
  
-   .NET 程序集：System.BizTalk:Assembly  
  
-   BAM 定义：System.BizTalk:Bam  
  
-   BizTalk 程序集：System.BizTalk:BizTalkAssembly  
  
-   BizTalk 绑定文件：System.BizTalk:BizTalkBinding  
  
-   安全证书：System.BizTalk:Certificate  
  
-   COM 组件：System.BizTalk:Com  
  
-   特别文件：System.BizTalk:File  
  
-   后续处理脚本：System.BizTalk:PostProcessingScript  
  
-   预处理脚本：System.BizTalk:PreProcessingScript  
  
-   策略或规则：System.BizTalk:Rules  
  
-   虚拟目录：System.BizTalk:WebDirectory  
  
> [!NOTE]
>  若要避免命名空间冲突，始终应而不是类型名称 （如程序集） 中使用的完整类型名称 （如 system.biztalk: assembly)。  
  
## <a name="usage"></a>用法  
 **BTSTask ListTypes**  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)