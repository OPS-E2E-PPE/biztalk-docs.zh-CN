---
title: MQSeries 适配器的命令行配置向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], Command-Line Configuration Wizard
- Command-Line Configuration Wizard
- MQSeries adapters, Command-Line Configuration Wizard
ms.assetid: cab905d1-fe19-4d6a-be1b-f561e133e1d2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 174e40f413be4ae3fab89965b842dee8fb8ba513
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357718"
---
# <a name="command-line-configuration-wizard-for-the-mqseries-adapter"></a>MQSeries 适配器的命令行配置向导
该向导具有四个选项用于安装、 卸载和日志记录操作。  
  
## <a name="syntax"></a>语法  
 **mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**  
  
|Option|Description|  
|------------|-----------------|  
|**/u**|卸载 MQSAgent。|  
|**/i** *config.xml*|安装在文件中使用的信息 MQSAgent *config.xml*。|  
|**/l** *logfile*|记录到文件的操作*日志文件*。|  
|**/?**|显示说明命令行选项的对话框。|  
  
 包含配置信息的 XML 文件的内容可能不同，具体取决于正在使用的 Windows 版本。 有关配置文件格式的详细信息，请参阅[MQSeries 适配器的 XML 配置文件](../core/xml-configuration-file-for-the-mqseries-adapter.md)。  
  
> [!IMPORTANT]
>  运行配置向导时，适配器不会正常工作。  
  
> [!NOTE]
>  您不能使用命令行配置向导重新配置 MQSAgent。 必须先运行向导以卸载代理 (**/u**)，然后运行它来配置 (**/i**)。  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器的无提示配置](../core/silent-configuration-of-the-mqseries-adapter.md)