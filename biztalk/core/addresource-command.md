---
title: AddResource 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b09bd8d-5e07-4443-b626-60401a158540
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5d8831cbac23343186eb4df9959378cb49fe279
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360203"
---
# <a name="addresource-command"></a>AddResource 命令
在本部分中的主题提供 AddResource 命令的参数的参考的信息。 使用此命令使用的参数因你想要添加的项目的类型而异。 若要获取的项目类型的完整列表，请使用**ListTypes**命令，如中所述[ListTypes 命令](../core/listtypes-command.md)。  
  
 若要添加特定项目类型获取帮助，请键入以下命令：  
  
 **BTSTask AddResource /Type:**\<*类型名称*\> **/？**  
  
> [!NOTE]
>  如果要添加的项目具有很长的路径名称，包括文件名称，要将项目添加到应用程序的操作可能会失败。 路径不能超过 260 个字符。  
>   
>  如果添加操作失败，请在操作期间执行的所有操作都回滚，只不过如果添加此命令，并且如果进行了任何条目，条目不会删除从 Windows 注册表，程序集不会删除从全局程序集缓存。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [AddResource 命令：BizTalk 程序集](../core/addresource-command-biztalk-assembly.md)  
  
-   [AddResource 命令：BizTalk 绑定](../core/addresource-command-biztalk-binding.md)  
  
-   [AddResource 命令：.NET 程序集](../core/addresource-command-net-assembly.md)  
  
-   [AddResource 命令：BAM 项目](../core/addresource-command-bam-artifact.md)  
  
-   [AddResource 命令：证书](../core/addresource-command-certificate.md)  
  
-   [AddResource 命令：COM 组件](../core/addresource-command-com-component.md)  
  
-   [AddResource 命令：文件](../core/addresource-command-file.md)  
  
-   [AddResource 命令：预处理脚本](../core/addresource-command-preprocessing-script.md)  
  
-   [AddResource 命令：后续处理脚本](../core/addresource-command-postprocessing-script.md)  
  
-   [AddResource 命令：策略](../core/addresource-command-policy.md)  
  
-   [AddResource 命令：虚拟目录](../core/addresource-command-virtual-directory.md)