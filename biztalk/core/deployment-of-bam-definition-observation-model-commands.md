---
title: 部署的 BAM 定义 （观察模式） 命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df7914f3-7a92-4ab2-bd0e-94a2eed4825e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dba1e1a4f54b3b33ebca8297cfe9beef7c4f868
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973187"
---
# <a name="deployment-of-bam-definition-observation-model-commands"></a>部署的 BAM 定义 （观察模式） 命令
您可借助 BAM 管理实用程序部署命令来应用、修改和删除定义。  
  
-   部署所有： 将部署的 BAM 定义。  
  
-   更新所有： BAM 定义更新。  
  
-   删除 all： 删除 BAM 定义。  
  
-   更新 livedataworkbook： 更新实时数据工作簿中的数据库连接信息。  
  
-   重新生成 livedataworkbook： 重新生成服务器上的实时数据工作簿。  
  
> [!NOTE]
>  你可以通过包括启用任何 BM 实用工具命令的跟踪 **-跟踪： 在 &#124; 关闭**参数交换机。 使用 Trace 开关将重写配置文件中的跟踪设置。 该开关可与所有标准 BM 命令一起使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="deploy-all-command"></a>deploy-all 命令  
 **用法**  
  
 **bm.exe 部署所有-DefinitionFile:\<def 文件\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|DefinitionFile:\<def 文件\>|包含要部署的定义的文件的路径和名称。|  
|服务器：\<服务器\>|可选： 要将定义部署到服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 要将定义部署到数据库的名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 将指定 BAM 定义 XML 文件中的所有项目部署到指定的服务器和数据库。 该文件可以是包含 BAM 定义 XML 的文本文件，也可以是 BAM Excel 工作簿。 该定义文件必须仅包含新项目。 如果该文件包含已部署的项目，部署将会失败并报告错误。  
  
 **部署 BAM 定义注意事项**  
  
 在部署警报订阅时，必须以“域\用户”格式指定订户的用户 ID。  
  
 必须在其上的计算机上运行的分布式的事务协调器 (DTC) 服务**部署所有**发出命令。  
  
 在部署定义时，BAM 管理实用程序仅在实时聚合 (RTA) 视图中支持 14 个维度级别。 部署超过此数量的级别将返回部署失败的错误。  
  
 如果定义了多个视图，它们使用不同的语言设置，然后将解决方案部署到使用单一语言的服务器中，则这些视图将无法部署。 这种方案只在没有计划聚合需要 BAM 定义中包含 OLAP 的情况下才支持。  
  
 启用 BAM 警报后，BAM 管理实用程序将已部署的活动视图限制为 49 个。 活动视图数的计算方法如下：各视图（1 至 N）乘以相应父活动的数量，然后将所得结果相加。  例如，如果部署了一个基于两个活动的视图，则结果为两个活动视图。  如果部署了两个视图，其中一个视图涉及两个活动，另一个视图基于一个活动，则您有 3 个活动视图。  
  
 对于具有多个数据透视表的 BAM 定义，如果这些数据透视表是在相同 RTA 和多维数据集名称组合的基础上定义的，则 BAM 管理实用程序不允许部署这种 BAM 定义。 Bm.exe 将终止部署并返回以下错误：  
  
 正在部署视图...错误： BAM 部署失败。  
  
 对于一个给定的 RTA 和多维数据集，只能定义一个数据透视表视图。  
  
 下列名称是保留名称，如果使用会导致定义部署失败：  
  
-   RecordID  
  
-   ActivityID  
  
-   IsVisible  
  
-   IsComplete  
  
-   LastModified  
  
> [!NOTE]
>  如果 bm.exe 在部署过程中遇到错误，部署将终止，对视图和活动的更改也会回滚。 对 OLAP 多维数据集的更改不会回滚，这是因为 OLAP 不支持事务性部署。  
  
> [!NOTE]
>  在使用一种区域设置的计算机上创建的 BAM 定义无法部署到配置为另一种区域设置的计算机上。 例如，在配置为英语区域设置的计算机上用英文版 Microsoft Excel 生成的 BAM 定义，无法部署到用日语区域设置配置为日文的计算机上。  
  
 **示例**  
  
```  
bm.exe deploy-all -DefinitionFile:MyDef.xml  
bm.exe deploy-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-all-command"></a>update-all 命令  
 **用法**  
  
 **bm.exe 更新所有-DefinitionFile:\<def 文件\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|DefinitionFile:\<def 文件\>|包含执行更新所用定义的文件的路径和名称。|  
|服务器：\<服务器\>|可选： 要将定义更新部署到服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 要将定义更新部署到数据库的名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 更新 BAM 定义 XML 中的某些项目。 该文件可以是包含 BAM 定义 XML 的文本文件，也可以是 BAM Excel 工作簿。 更新不会删除当前定义文件中没有描述的项目。 更新可以将新检查点添加到活动中，但是不能从已部署的活动中删除检查点。 更新既不能重命名检查点，也不能更改检查点的属性。  
  
 部署某个活动后，对该活动可执行的操作就会受到限制。 具体而言，除非准备让管理员取消部署整个 BAM 活动和视图集，然后重新部署它们，否则，您无法从活动中删除项。 这可能导致查看中断和数据丢失，除非管理员进行数据备份和还原。  
  
> [!NOTE]
>  您不能使用此命令向现有视图添加新活动。 若要将视图添加到活动中，必须创建包含新活动的新视图。 然后可以取消部署旧视图，但是要知道，您将丢失 OLAP 数据历史记录。  
  
 **示例**  
  
```  
bm.exe update-all -DefinitionFile:MyDef.xml  
bm.exe update-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="remove-all-command"></a>remove-all 命令  
 **用法**  
  
 **bm.exe 删除全部 DefinitionFile:\<def 文件\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|DefinitionFile:\<def 文件\>|包含要删除的定义的文件的路径和名称。|  
|服务器：\<服务器\>|可选： 将从中删除定义的服务器的名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 定义将从中删除数据库的名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 删除在 BAM 定义 XML 文件中指定的所有项目。 该文件可以是包含 BAM 定义 XML 的文本文件，也可以是 BAM Excel 工作簿。 每个项目的定义必须与部署所用的初始定义完全匹配。  
  
 **示例**  
  
```  
bm.exe remove-all -DefinitionFile:MyDef.xml  
bm.exe remove-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-livedataworkbook-command"></a>update-livedataworkbook 命令  
 **用法**  
  
 **bm.exe 更新 livedataworkbook-名称：\<livedata 工作簿文件名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|名称：\<livedata 工作簿\>|要更新的现有活动工作簿的名称。|  
|服务器：\<服务器\>|可选： 工作簿所驻留的服务器名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上工作簿所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 更新指定 BAM 实时数据工作簿中的 BAM 主导入数据库连接信息。  
  
> [!NOTE]
>  配置新连接字符串时，必须重新启动 TDDS 服务，才能确保服务能够识别出该更改。 TDDS 服务的详细信息，请参阅[BAM 事件总线服务存储过程](../core/bam-event-bus-service-stored-procedures.md)。  
  
 **示例**  
  
```  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls -Server:SalesSrv  
```  
  
## <a name="regenerate-livedataworkbook-command"></a>regenerate-livedataworkbook 命令  
 **用法**  
  
 **bm.exe 重新生成 livedataworkbook WorkbookName:\<livedata 工作簿文件名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**  
  
 **参数**  
  
|参数|Description|  
|---------------|-----------------|  
|WorkbookName:\<livedata 工作簿文件名称\>|要更新的工作簿的名称。|  
|服务器：\<服务器\>|可选： 工作簿所驻留的服务器名称。 服务器必须是从中运行 bm.exe 计算机位于同一域中。 如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。|  
|数据库：\<数据库\>|可选： 在其上工作簿所在的数据库名称。 如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 生成 BAM 实时数据工作簿，但不部署该工作簿。  
  
 示例  
  
```  
bm.exe regenerate-livedataworkbook -WorkbookName:SalesManager_Live.xls  
bm.exe regenerate-livedataworkbook -WorkbookName:SM_Live.xls -Server:S1  
```  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)