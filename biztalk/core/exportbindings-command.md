---
title: ExportBindings 命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6573142e-7ca7-4990-98e3-b7a54840da13
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f12e28b68698aeb42aefa387c94bd76470ecaf8
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="exportbindings-command"></a>ExportBindings 命令
导出绑定 BizTalk 程序集、 应用程序或组。 你还可以导出全局方以及程序集，应用程序或组绑定的绑定。 （当事方是组织的所有实体，例如你的合作伙伴与业务流程交互。）  
  
## <a name="usage"></a>用法  
 **BTSTask ExportBindings /Destination:** *值*[**/GroupLevel**] [**/ApplicationName: * **值*] [**/程序集名称：***值*] &#124; [**/GlobalParties**] [**/Server:***值 *] [* * / 数据库：***值 *]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|“值”|  
|---------------|--------------|-----------|  
|**/ 目标** (或 **/De**, ，请参阅备注)|是|要创建的绑定文件的完整路径，包含文件名。 如果已存在具有相同路径的绑定文件，则该文件将被覆盖。 如果路径包含空格，必须将它括在双引号 （"）。|  
|**/ GroupLevel** (或 **/Gr**, ，请参阅备注)|否|如果指定，将导出的当前组中的所有绑定。 你可以指定以下三个参数之一︰ GroupLevel、 应用程序名称或程序集名称。|  
|**/ ApplicationName** (或 **/Ap**, ，请参阅备注)|否|要导出的绑定应用程序的名称。 应用程序必须存在。 如果名称包含空格，则必须将它用双引号 （"）。 若要验证应用程序名称，可以使用**ListApps**命令时中, 所述[ListApps 命令](../core/listapps-command.md)。 如果未指定此参数，则使用默认 BizTalk 应用程序。 你可以指定以下三个参数之一︰ GroupLevel、 应用程序名称或程序集名称。|  
|**/ AssemblyName** (或 **/As**, ，请参阅备注)|否|要从中导出绑定程序集的本地唯一标识符 (LUID)。 可以通过应用程序中查看项目的列表的 Luid [ListApp 命令](../core/listapp-command.md)。 你可以指定以下三个参数之一︰ GroupLevel、 应用程序名称或程序集名称。|  
|**/ GlobalParties** (或 **/Gl**, ，请参阅备注)|否|如果指定，将导出组的全局参与方信息。|  
|**/ 服务器** (或 **/S**, ，请参阅备注)|否|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库** (或 **/Da**, ，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml"GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [导出绑定](../core/exporting-bindings6.md)