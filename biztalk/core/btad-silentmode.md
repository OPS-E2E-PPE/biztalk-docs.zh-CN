---
title: "BTAD_SilentMode |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTAD_SilentMode [environment variable], about BTAS_SilentMode
- BTAD_SilentMode [environment variable]
- BTAD_SilentMode [environment variable], warnings
ms.assetid: 271835cf-1587-44c5-b5af-b4df4e981ab4
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31715835c98d2f60a3b5f1c18251571ea57641d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="btadsilentmode"></a>BTAD_SilentMode
BTAD_SilentMode 为以无提示模式运行脚本指定一些选项。  
  
## <a name="remarks"></a>注释  
 在您为无提示模式指定选项时，BTS Installer 会将其值置于 BTAD_SilentMode 变量中。  
  
 BTAD_SilentMode 的默认值为 2，指定脚本以无提示模式运行。 下表描述 BTAD_SilentMode 的可能值。  
  
> [!CAUTION]
>  如果您从脚本启动 BizTalk Server 用户界面，则模式对话框可能不可见或没有焦点，因此导致这些对话框难于查看和关闭。 在模式对话框打开时，BizTalk 数据库可能会被锁定并且无法访问。 因此，在生产系统上，所有脚本都应以无提示模式运行。  
  
|值|说明|  
|-----------|-----------------|  
|0|不更改用户界面 (UI) 级别。|  
|1|使用默认用户界面级别。|  
|2|执行无提示安装（默认设置）。|  
|3|提供简单的进度和错误处理。|  
|4|提供创作的用户界面，不显示向导。|  
|0x80|如果与上述任何值一起使用，则在当脚本已成功执行或存在错误时，Windows Installer 将显示一个模式对话框。 如果用户取消该操作，则不会显示任何对话框。|  
|0x40|如果与值 3 一起使用，则 Windows Installer 将显示进度对话框，但不显示任何模式对话框或错误对话框。|  
|0x20|如果与值 3 一起使用，则 Windows Installer 将显示进度对话框，但不显示任何模式对话框或错误对话框。|  
|0x100|如果与值 3 一起使用，则 Windows Installer 将显示进度对话框，但不显示任何模式对话框或错误对话框。|  
  
## <a name="see-also"></a>另请参阅  
 [前期和后期处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md)   
 [环境变量如何指示部署状态](../core/how-environment-variables-indicate-deployment-state.md)