---
title: 部署 BAM 定义 （观察模型） 命令 |Microsoft Docs
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
ms.openlocfilehash: 506b563136fec86fdde9aebab31ad9bb4435736b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351742"
---
# <a name="deployment-of-bam-definition-observation-model-commands"></a>部署的 BAM 定义 （观察模型） 命令
BAM 管理实用程序部署命令，可将应用、 修改和删除定义。  
  
-   部署所有：部署 BAM 定义。  
  
-   更新所有：更新 BAM 定义。  
  
-   全部删除：删除 BAM 定义。  
  
-   更新 livedataworkbook:更新实时数据工作簿中的数据库连接信息。  
  
-   重新生成 livedataworkbook:重新生成实时数据工作簿的服务器上。  
  
> [!NOTE]
>  通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。 使用 Trace 开关将重写配置文件中的跟踪设置。 此开关可以与所有标准 BM 命令结合使用。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="deploy-all-command"></a>deploy-all 命令  
 **Usage**  
  
 **bm.exe deploy-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|DefinitionFile:\<def 文件\>|路径和包含要部署的定义文件的名称。|  
|服务器：\<服务器\>|可选：向其部署定义的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：向其部署定义的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 将部署到指定的服务器和数据库指定 BAM 定义 XML 文件中的所有项目。 文件可以是包含 BAM 定义 XML 文件或 BAM Excel 工作簿的文本文件。 定义文件必须仅包含新项目。 如果该文件包含已部署的项目，部署将失败并报告错误。  
  
 **部署 BAM 定义的注意事项**  
  
 在部署警报订阅时，必须以 domain\user 格式指定用户的订阅服务器的 Id。  
  
 分布式的事务处理协调器 (DTC) 服务必须在其上的计算机上运行**部署所有**发出命令。  
  
 部署定义时，BAM 管理实用程序仅在实时聚合 (RTA) 视图中支持 14 个维度级别。 部署其他级别返回部署失败的错误。  
  
 如果定义多个使用不同的语言设置并将你的解决方案部署到使用一种语言的服务器的视图，视图将无法部署。 仅在您不需要计划的聚合需要 BAM 定义的一部分的 OLAP 的情况下支持此方案。  
  
 BAM 管理实用程序限制为 49 已部署的活动视图启用 BAM 警报时也是如此。 活动视图数计算为求和方法 1..N 乘以的父活动数。  例如，如果部署基于两个活动的视图，您将获得两个活动视图。  如果部署两个视图，其中一个跨越两个活动和其他基于单个活动，您有 3 个活动视图。  
  
 BAM 管理实用程序块部署 BAM 定义具有多个数据透视表报告上的相同 RTA 和多维数据集名称组合所定义。 Bm.exe 将终止部署并返回以下错误：  
  
 正在部署视图...错误：BAM 部署失败。  
  
 可以在给定的 RTA 和多维数据集上定义只有一个数据透视表视图。  
  
 下面的列表的名称是保留，并将导致定义部署失败：  
  
-   RecordID  
  
-   ActivityID  
  
-   IsVisible  
  
-   IsComplete  
  
-   LastModified  
  
> [!NOTE]
>  如果 bm.exe 在部署过程中遇到错误，部署将终止并回滚对视图和活动的更改。 对 OLAP 多维数据集的更改不会回滚，因为 OLAP 不支持事务性部署。  
  
> [!NOTE]
>  使用一种区域设置的计算机上创建的 BAM 定义无法部署到使用不同的区域设置设置配置的计算机。 例如，不能配置为日文使用日语区域设置的计算机上部署生成配置为英语区域设置的计算机上使用英语语言版本的 Microsoft Excel 的 BAM 定义。  
  
 **示例**  
  
```  
bm.exe deploy-all -DefinitionFile:MyDef.xml  
bm.exe deploy-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-all-command"></a>update-all 命令  
 **Usage**  
  
 **bm.exe update-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|DefinitionFile:\<def 文件\>|路径和包含要执行更新定义的文件的名称。|  
|服务器：\<服务器\>|可选：要将定义更新部署到服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：向其部署定义更新的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 更新 BAM 定义 XML 中的某些项目。 文件可以是包含 BAM 定义 XML 文件或 BAM Excel 工作簿的文本文件。 更新不会删除当前定义文件中未描述的项目。 它可以将新的检查点添加到活动，但无法从已部署的活动中删除检查点。 更新既不重命名检查点也不能更改检查点属性。  
  
 活动部署后，可在活动执行的操作就会受到限制。 具体而言，除非你已准备好让管理员取消部署整个 BAM 活动和视图集，然后重新部署它们，否则您不能从活动中删除项目。 除非管理员进行备份，这可能导致查看中断和数据丢失的数据和还原。  
  
> [!NOTE]
>  不能使用此命令将新活动添加到现有视图。 若要向活动中添加一个视图，必须创建一个包含新活动的新视图。 然后，您可以取消部署旧视图，但请注意，您将丢失 OLAP 数据历史记录。  
  
 **示例**  
  
```  
bm.exe update-all -DefinitionFile:MyDef.xml  
bm.exe update-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="remove-all-command"></a>remove-all 命令  
 **Usage**  
  
 **bm.exe remove-all DefinitionFile:\<def file\> [ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|DefinitionFile:\<def 文件\>|路径和包含要删除的定义文件的名称。|  
|服务器：\<服务器\>|可选：要从中删除定义的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：要从中删除定义的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 删除 BAM 定义 XML 文件中指定的所有项目。 文件可以是包含 BAM 定义 XML 文件或 BAM Excel 工作簿的文本文件。 每个项目的定义必须与部署所用的原始定义完全匹配。  
  
 **示例**  
  
```  
bm.exe remove-all -DefinitionFile:MyDef.xml  
bm.exe remove-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-livedataworkbook-command"></a>update-livedataworkbook 命令  
 **Usage**  
  
 **bm.exe update-livedataworkbook -Name:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|名称：\<实时数据工作簿\>|要更新的现有实时工作簿的名称。|  
|服务器：\<服务器\>|可选：该工作簿所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：该工作簿所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 更新指定 BAM 实时数据工作簿中的 BAM 主导入数据库连接信息。  
  
> [!NOTE]
>  配置新的连接字符串时，必须重新启动 TDDS 服务，以确保服务识别出该更改。 有关 TDDS 服务的详细信息，请参阅[BAM 事件总线服务存储过程](../core/bam-event-bus-service-stored-procedures.md)。  
  
 **示例**  
  
```  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls -Server:SalesSrv  
```  
  
## <a name="regenerate-livedataworkbook-command"></a>regenerate-livedataworkbook 命令  
 **Usage**  
  
 **bm.exe regenerate-livedataworkbook -WorkbookName:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **Parameters**  
  
|参数|Description|  
|---------------|-----------------|  
|WorkbookName:\<实时数据工作簿文件名称\>|要更新的工作簿的名称。|  
|服务器：\<服务器\>|可选：该工作簿所驻留的服务器的名称。 服务器必须位于与运行 bm.exe 的计算机位于同一域中。 如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。|  
|数据库：\<数据库\>|可选：该工作簿所驻留的数据库的名称。 如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。|  
  
 生成 BAM 实时数据工作簿，但不部署该工作簿。  
  
 示例  
  
```  
bm.exe regenerate-livedataworkbook -WorkbookName:SalesManager_Live.xls  
bm.exe regenerate-livedataworkbook -WorkbookName:SM_Live.xls -Server:S1  
```  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)