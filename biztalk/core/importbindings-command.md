---
title: ImportBindings 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b8dd1ee-1719-4cd1-b503-b004f312daeb
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f0a641c92e3917c6c063587248db3cfaba63048
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332111"
---
# <a name="importbindings-command"></a>ImportBindings 命令
将绑定从基于 XML 的绑定文件导入到 BizTalk 应用程序或组。 绑定可能已从导出的程序集、 应用程序或组，如中所述[导出绑定](../core/exporting-bindings6.md)。 根据从其绑定的导出的位置，ApplicationName 和 GroupLevel 参数具有不同的作用。 有关详细信息，请参阅本主题后面的“备注”。  
  
> [!NOTE]
>  绑定文件中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不具有指定的应用程序。 它们是导入到默认应用程序。  
  
## <a name="usage"></a>用法  
 **BTSTask ImportBindings-源**:*值*[**-GroupLevel** &#124; **-ApplicationName**:*值*] [**-服务器**:*值*] [**-数据库**:*值*] [**-ImportTrackingSettings**:*值*] [**-ExcludeParties**]
  
## <a name="parameters"></a>Parameters  
  
|                   参数                   | Required |                                                                                                                                                                                                                                                         ReplTest1                                                                                                                                                                                                                                                          |
|-----------------------------------------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **-源**(或 **-因此**，请参阅备注)     | Required |                                                                                                                                                                                          要导入，其中包括文件名的绑定文件的完整路径。 包含空格的路径必须括在引号 （"）。                                                                                                                                                                                          |
|   **-GroupLevel** (或 **-G**，请参阅备注)    | 可选 |                                                                                                                                                                                               绑定文件导入到当前组的选项。 如果指定此参数，则不要指定 /ApplicationName。                                                                                                                                                                                                |
| **-ApplicationName** (或 **-A**，请参阅备注) | 可选 |                                                                          在其中绑定是要导入 BizTalk 应用程序的名称。 如果名称包含空格，必须将其用双引号 （"）。 该应用程序必须存在，或导入操作将失败。 如果未指定此参数，则使用默认 BizTalk 应用程序。 如果指定此参数，则不要指定 /GroupLevel。                                                                           |
|     **服务器**(或 **-Se**，请参阅备注)     | 可选 | 承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。 |
|    **-数据库**(或 **-D**，请参阅备注)     | 可选 |                                                                                                                                                                                    BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。                                                                                                                                                                                     |
|          **-ImportTrackingSettings**          | 可选 |                                                                                                                                           新开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 <br /><br />此设置将替代全局跟踪设置导入选项。 "True"值，则允许导入跟踪设置。 False 不允许导入跟踪设置。                                                                                                                                           |
|              **-ExcludeParties**              | 可选 |                                                                                                                                                                                 新开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 <br /><br />如果指定，系统会从绑定文件中排除参与方信息。                                                                                                                                                                                  |
  
## <a name="sample"></a>示例  
 以下命令将绑定导入到默认 BizTalk 组中名为 MyApplication 的应用程序。  
  
`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml`
  
 以下命令将绑定导入到名为 MY_Server 的 SQL Server 实例上运行的 BizTalk 管理数据库中定义的组。  
  
 `BTSTask ImportBindings -GroupLevel -Server:MY_Server -Database:BiztalkMgmtDb -Source:C:\Bindings\Binding1.xml`
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
 绑定可能已从程序集、 应用程序或组导出。 下表中所示，具体取决于从绑定的导出位置，ApplicationName 和 GroupLevel 参数具有不同的作用。  
  
|绑定源|ApplicationName 参数的效果|GroupLevel 参数的效果|  
|----------------------------|-----------------------------------------------|------------------------------------------|  
|从程序集导出的绑定|在应用程序名称中指定的应用程序必须包含与从中导出绑定文件的程序集同名的程序集。 否则，导入操作将失败。|当前组必须包含程序集和具有相同名称的程序集和从中导出绑定文件的应用程序作为应用程序。 否则，导入将失败。|  
|从应用程序导出的绑定|从中导出绑定文件的应用程序必须与 ApplicationName 指定的应用程序相同的名称。 否则，导入操作将失败。|从中导出绑定文件的应用程序必须在其中导入绑定在组中具有与应用程序相同的名称。 否则，导入操作将失败。|  
|从组导出的绑定|从中导出绑定文件的组必须包含与 ApplicationName 指定的应用程序同名的应用程序。 否则，导入操作将失败。|绑定将导入对应的应用程序。 换而言之，从中导出绑定的组中的应用程序的绑定将导入到当前组中具有相同名称的应用程序。|  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何将绑定导入 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)   
 [如何将绑定导入 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)