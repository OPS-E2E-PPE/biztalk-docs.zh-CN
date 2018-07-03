---
title: BAM 管理实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c55aabe2-f38b-4917-863c-b408a4eef98e
caps.latest.revision: 50
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c27483ac7200677f29841732571c67cd00eb6d42
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000366"
---
# <a name="bam-management-utility"></a>BAM 管理实用程序
负责业务活动监视 (BAM) 定义的管理员使用 BAM 管理实用程序来管理和维护 BAM 基础结构的各个方面。  
  
 使用 BAM 实用程序可以执行以下任务：  
  
-   将 BAM 定义和 BAM 配置 XML 用作输入。 BAM 定义 XML 文件或 XLS 文件定义了要跟踪和聚合的数据，以及所跟踪数据的业务最终用户视图。 BAM 配置 XML 规定了部署基础结构的位置，例如，服务器名、数据库名以及其他数据库设置。  
  
-   在服务器上部署运行时基础结构，其中包括 BAM 主导入数据库、BAM 星型架构数据库、BAM 分析数据库及相应的数据转换服务 (DTS) 包。 以下各项是在此步骤中创建的：  
  
    -   BAM 主导入数据库  
  
    -   BAM 星型架构数据库  
  
    -   BAM 存档数据库  
  
    -   BAM 分析数据库  
  
> [!NOTE]
>  运行 BAM 管理实用程序的计算机的区域设置必须与创建要部署的 BAM 定义所用的区域设置相同，这样 BAM 命令才能正常使用。 例如，如果您执行**get 视图**命令配置的计算机上为英语区域设置，而数据库使用法语区域设置的计算机上你将不能使用返回的视图名称，除非您重置你计算机为法语的区域设置。  
  
 使用 BAM 管理实用程序可以在服务器上生成并部署跟踪配置。 BAM 管理实用程序是一个命令行工具位于\<*安装路径*\>\Program Files\Microsoft BizTalk Server\<版本\>\Tracking\BM.exe。  
  
> [!IMPORTANT]
>  若要运行 BAM 管理实用程序，您必须隶属**db_owner** BAM 主导入、 BAM 星型架构和 BAM 存档数据库中的 SQL Server 数据库角色。 执行与 BAM 警报有关的任何更新时，你还必须对 BAM 警报数据库具有 sysadmin 权限。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
## <a name="bam-management-utility-commands"></a>BAM 管理实用程序命令  
 命令说明使用以下约定：  
  
- 方括号 ([]) 表示可选参数。  
  
- 尖括号 (<>) 表示必需的参数。  
  
- 大括号 ({}) 指示应从枚举列表中选择一项。  
  
- 安全帐户可以是 NT 组帐户，也可以是单个 NT 用户帐户。  
  
- BAM 定义文件可以是 XML 文件，也可以是 BAM Excel 工作簿文件 (.xls)。  
  
- 如果未提供 BAM 配置文件，则默认为是当前文件夹中的 BamConfiguration.xml。  
  
  各个命令说明包含在以下主题中：  
  
- [数据库命令](../core/database-commands.md)  
  
- [BAM 定义（观察模型）部署命令](../core/deployment-of-bam-definition-observation-model-commands.md)  
  
- [基础结构管理命令](../core/infrastructure-management-commands.md)  
  
- [活动管理命令](../core/activity-management-commands.md)  
  
- [视图管理命令](../core/view-management-commands.md)  
  
- [警报管理命令](../core/alert-management-commands.md)  
  
- [用户管理命令](../core/user-management-commands.md)  
  
- [警报订阅管理命令](../core/alert-subscription-management-commands.md)  
  
- [侦听器管理命令](../core/interceptor-management-commands.md)  
  
## <a name="displaying-the-bam-management-utility-help"></a>显示 BAM 管理实用程序帮助  
 您使用 **/？** 或**帮助 BAM 管理实用程序**命令以显示 BAM 管理实用程序的帮助文件。  
  
#### <a name="to-display-the-help-file-for-the-bam-management-utility"></a>显示 BAM 管理实用程序的帮助文件  
  
1.  从命令提示符处，浏览到以下目录： C:\Program Files\Microsoft BizTalk Server\<版本\>\Tracking\\。  
  
2.  类型**bm**或**bm 帮助**。  
  
3.  按 Enter。