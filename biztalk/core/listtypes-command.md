---
title: 默认应用命令 |Microsoft 文档
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
ms.openlocfilehash: afe2519fc5507ae0975d050a998faec78f2940a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262213"
---
# <a name="listtypes-command"></a>默认应用命令
列出的所有项目类型可添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用**AddResource**命令。 有关详细信息**AddResource**命令，请参阅[AddResource 命令](../core/addresource-command.md)。  
  
 受支持的项目类型的完全限定名称如下所示：  
  
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
>  为了避免命名空间冲突，应该始终使用完整的类型名称（如 System.BizTalk:Assembly），而不应只使用类型名（如 Assembly）。  
  
## <a name="usage"></a>用法  
 **BTSTask 默认应用**  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)