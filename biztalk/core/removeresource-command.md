---
title: RemoveResource 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e2c6046-43d4-4ac1-a1b1-3795b4e44038
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc7b5e6f5d254624f295aef16761d074379f3ea6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397915"
---
# <a name="removeresource-command"></a>RemoveResource 命令
移除 （删除） 从 BizTalk 管理数据库项目。 运行此命令不会删除该项目从全局程序集缓存 (GAC)、 文件系统、 证书存储区、 Internet 信息服务或 Windows 注册表中，如果它存在于这些位置中。 不会从 BAM 主导入数据库中删除 BAM 定义，也不会删除策略从规则引擎数据库。 如果运行此命令删除绑定文件，则绑定保持不变，删除只绑定文件。  
  
 您可以使用此命令删除以下项目类型：  
  
- .NET 程序集 (system.biztalk: assembly)  
  
- BAM 定义 (system.biztalk: bam)  
  
- BizTalk 程序集 (system.biztalk: biztalkassembly  
  
- BizTalk 绑定文件 (system.biztalk: biztalkbinding)  
  
- 安全证书 (system.biztalk: certificate)  
  
- COM 组件 (system.biztalk: com)  
  
- 特别文件 (system.biztalk: file)  
  
- 后续处理脚本 (system.biztalk: postprocessingscript)  
  
- 预处理脚本 (system.biztalk: preprocessingscript)  
  
- 策略或规则 (system.biztalk: rules)  
  
- 虚拟目录 (system.biztalk: webdirectory)  
  
  在以下情况下，删除操作将失败：  
  
- 尝试删除 BizTalk 程序集到另一个程序集具有的引用。  
  
- 尝试删除包含由发送管道的 BizTalk 程序集或接收端口。  
  
- 尝试删除包含发送端口所使用的映射的 BizTalk 程序集。  
  
- 尝试删除包含业务流程的未处于已取消登记状态或具有挂起的实例的 BizTalk 程序集。  
  
## <a name="usage"></a>用法  
 **BTSTask RemoveResource /ApplicationName:** *value* **/Luid:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|Description|  
|---------------|--------------|-----------------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|是|包含的资源项目的 BizTalk 应用程序若要删除的名称。 如果名称包含空格，必须将其用双引号 （"）。|  
|**/ Luid** (或 **/L**，请参阅备注)|是|项目的本地唯一标识符 (LUID)。 可通过获得 LUID [ListApp 命令](../core/listapp-command.md)。|  
|**/ 服务器**(或 **/S**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何从应用程序中删除项目](../core/how-to-remove-an-artifact-from-an-application.md)