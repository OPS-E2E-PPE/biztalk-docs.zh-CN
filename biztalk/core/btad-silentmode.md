---
title: BTAD_SilentMode |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAD_SilentMode [environment variable], about BTAS_SilentMode
- BTAD_SilentMode [environment variable]
- BTAD_SilentMode [environment variable], warnings
ms.assetid: 271835cf-1587-44c5-b5af-b4df4e981ab4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9433dde06cf40b0c7c94091f48af4f4b37f9bdf2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357813"
---
# <a name="btadsilentmode"></a>BTAD_SilentMode
BTAD_SilentMode 指定在静默模式下运行该脚本的选项。  
  
## <a name="remarks"></a>备注  
 当指定为无提示模式的选项时，BTS Installer 会置于 BTAD_SilentMode 变量将其值。  
  
 BTAD_SilentMode 的默认值为 2，它指定在静默模式下运行该脚本。 下表描述 btad_silentmode 的可能值。  
  
> [!CAUTION]
>  如果从脚本启动 BizTalk Server 用户界面，模式对话框可能不可见或没有焦点，使它们难以查看和解除。 当模式对话框打开时，会锁定且无法访问 BizTalk 数据库。 出于此原因，在生产系统中，应以静默模式运行所有脚本。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|0|不会更改用户界面 (UI) 级别。|  
|1|使用默认用户界面级别。|  
|2|执行无提示安装 （默认值）。|  
|3|提供了简单的进度和错误处理。|  
|4|提供创作的用户界面;不显示向导。|  
|0x80|如果与上述任何值一起使用，Windows 安装程序将显示模式对话框，如果已成功执行脚本或已出现错误。 如果用户取消了操作，不显示任何对话框。|  
|0x40|如果与值 3 一起使用，Windows 安装程序将显示进度对话框，但不显示任何模式对话框或错误对话框。|  
|0x20|如果与值 3 一起使用，Windows 安装程序将显示进度对话框，但不显示任何模式对话框或错误对话框。|  
|0x100|如果与值 3 一起使用，Windows 安装程序将显示进度对话框，但不显示任何模式对话框或错误对话框。|  
  
## <a name="see-also"></a>请参阅  
 [预处理和后处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md)   
 [环境变量如何指示部署状态](../core/how-environment-variables-indicate-deployment-state.md)