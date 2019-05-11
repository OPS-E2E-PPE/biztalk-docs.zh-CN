---
title: ExportBindings 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6573142e-7ca7-4990-98e3-b7a54840da13
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0dc0ce7fb54e15028adb76a8edf34d125c064ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345931"
---
# <a name="exportbindings-command"></a>ExportBindings 命令
导出 BizTalk 程序集、 应用程序，或组的绑定。 此外可以导出全局参与方以及程序集、 应用程序或组绑定的绑定。 （参与方是组织的所有实体，例如与业务流程进行交互的你，合作伙伴。）  
  
## <a name="usage"></a>用法  
 **BTSTask ExportBindings /Destination:** *值*[**/GroupLevel**] [**/ApplicationName:**<em>值</em>] [**/AssemblyName:**<em>值</em>] &#124; [**/GlobalParties**] [**/Server:**<em>值</em>] [**/Database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ 目标**(或 **/De**，请参阅备注)|是|若要创建，其中包括文件名的绑定文件的完整路径。 如果绑定文件具有相同的路径已存在，则将覆盖。 如果路径包含空格，则必须将其括在双引号 （"）。|  
|**/ GroupLevel** (或 **/Gr**，请参阅备注)|否|如果指定，将导出当前组中的所有绑定。 您可以指定以下三个参数之一：GroupLevel、 ApplicationName 或 AssemblyName。|  
|**/ ApplicationName** (或 **/Ap**，请参阅备注)|否|从中导出绑定的应用程序名称。 该应用程序必须存在。 如果名称包含空格，必须将其用双引号 （"）。 若要验证的应用程序名称，可以使用**ListApps**命令，如中所述[ListApps 命令](../core/listapps-command.md)。 如果未指定此参数，则使用默认 BizTalk 应用程序。 您可以指定以下三个参数之一：GroupLevel、 ApplicationName 或 AssemblyName。|  
|**/ AssemblyName** (或 **/As**，请参阅备注)|否|从中导出绑定程序集的本地唯一标识符 (LUID)。 可以通过应用程序中查看项目的 Luid 的列表[ListApp 命令](../core/listapp-command.md)。 您可以指定以下三个参数之一：GroupLevel、 ApplicationName 或 AssemblyName。|  
|**/ GlobalParties** (或 **/Gl**，请参阅备注)|否|如果指定，将导出组的全局参与方信息。|  
|**/ 服务器**(或 **/S**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/Da**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [导出绑定](../core/exporting-bindings6.md)