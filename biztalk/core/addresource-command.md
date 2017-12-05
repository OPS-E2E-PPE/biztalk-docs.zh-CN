---
title: "AddResource 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b09bd8d-5e07-4443-b626-60401a158540
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 875a087fa3afe7515aee2c406cbc47551bea1f4d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="addresource-command"></a>AddResource 命令
本部分中主题提供关于 AddResource 命令的参数的参考信息。 使用此命令使用的参数因你想要添加的项目的类型。 若要获取的项目类型的完整列表，请使用**默认应用**命令时中, 所述[默认应用命令](../core/listtypes-command.md)。  
  
 若要获得添加特定项目类型的帮助，请键入以下命令：  
  
 **BTSTask AddResource /Type:**\<*类型名称*\> **/？**  
  
> [!NOTE]
>  如果要添加的项目具有很长的路径名（包括文件名），则将项目添加到应用程序的操作可能失败。 路径名不能超过 260 个字符。  
>   
>  如果添加操作失败，除以下两种情况外，添加过程中执行的所有操作均被回滚：此命令添加到全局程序集缓存中的程序集不从全局程序集缓存中删除；在 Windows 注册表中添加的项不从注册表中删除。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [AddResource 命令：BizTalk 程序集](../core/addresource-command-biztalk-assembly.md)  
  
-   [AddResource 命令：BizTalk 绑定](../core/addresource-command-biztalk-binding.md)  
  
-   [AddResource 命令：.NET 程序集](../core/addresource-command-net-assembly.md)  
  
-   [AddResource 命令：BAM 项目](../core/addresource-command-bam-artifact.md)  
  
-   [AddResource 命令：证书](../core/addresource-command-certificate.md)  
  
-   [AddResource 命令：COM 组件](../core/addresource-command-com-component.md)  
  
-   [AddResource 命令：文件](../core/addresource-command-file.md)  
  
-   [AddResource 命令：预处理脚本](../core/addresource-command-preprocessing-script.md)  
  
-   [AddResource 命令：后期处理脚本](../core/addresource-command-postprocessing-script.md)  
  
-   [AddResource 命令：策略](../core/addresource-command-policy.md)  
  
-   [AddResource 命令：虚拟目录](../core/addresource-command-virtual-directory.md)