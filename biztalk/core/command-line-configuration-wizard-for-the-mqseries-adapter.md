---
title: "命令行配置向导为 MQSeries 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], Command-Line Configuration Wizard
- Command-Line Configuration Wizard
- MQSeries adapters, Command-Line Configuration Wizard
ms.assetid: cab905d1-fe19-4d6a-be1b-f561e133e1d2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee73b890fca43a3651f22092486e5898862b0b72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="command-line-configuration-wizard-for-the-mqseries-adapter"></a>MQSeries 适配器的命令行配置向导
该向导具有四个用于安装、卸载和记录操作的选项。  
  
## <a name="syntax"></a>语法  
 **mqsconfigwiz [/u] [/i config.xml] [/l 日志文件] [/？]**  
  
|选项|Description|  
|------------|-----------------|  
|**/u**|卸载 MQSAgent。|  
|**/i** *config.xml*|安装在文件中使用信息 MQSAgent *config.xml*。|  
|**/l** *日志文件*|会将操作记录到文件*日志文件*。|  
|**/?**|显示了对命令行选项进行说明的对话框。|  
  
 包含配置信息的 XML 文件的内容根据使用的 Windows 版本而可能会有所不同。 有关配置文件格式的详细信息，请参阅[MQSeries 适配器的 XML 配置文件](../core/xml-configuration-file-for-the-mqseries-adapter.md)。  
  
> [!IMPORTANT]
>  在运行该配置向导时，适配器将不能工作。  
  
> [!NOTE]
>  您不能用命令行配置向导重新配置 MQSAgent。 你必须先运行卸载代理向导 (**/u**)，然后运行该配置 (**/i**)。  
  
## <a name="see-also"></a>另请参阅  
 [无提示 MQSeries 适配器配置](../core/silent-configuration-of-the-mqseries-adapter.md)