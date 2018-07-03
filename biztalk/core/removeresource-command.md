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
ms.openlocfilehash: c95b636083542bb1291cd10881bd74ca9d41c15b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976990"
---
# <a name="removeresource-command"></a>RemoveResource 命令
从 BizTalk 管理数据库中删除项目。 运行此命令不会从全局程序集缓存 (GAC)、文件系统、证书存储、Internet 信息服务或 Windows 注册表中删除项目（如果项目存在于这些位置中）。 该命令不会从 BAM 主导入数据库中删除 BAM 定义，也不会从规则引擎数据库中删除策略。 如果您运行此命令来删除绑定文件，则绑定保持不变，仅删除绑定文件。  
  
 使用此命令可以删除以下项目类型：  
  
- .NET 程序集 (System.BizTalk:Assembly)  
  
- BAM 定义 (System.BizTalk:Bam)  
  
- BizTalk 程序集 (System.BizTalk:BizTalkAssembly)  
  
- BizTalk 绑定文件 (System.BizTalk:BizTalkBinding)  
  
- 安全证书 (System.BizTalk:Certificate)  
  
- COM 组件 (System.BizTalk:Com)  
  
- 特别文件 (System.BizTalk:File)  
  
- 后续处理脚本 (System.BizTalk:PostProcessingScript)  
  
- 预处理脚本 (System.BizTalk:PreProcessingScript)  
  
- 策略或规则 (System.BizTalk:Rules)  
  
- 虚拟目录 (System.BizTalk:WebDirectory)  
  
  在以下情况下，删除操作会失败：  
  
- 尝试删除其他程序集要引用的 BizTalk 程序集。  
  
- 尝试删除包含发送端口或接收端口所使用的管道的 BizTalk 程序集。  
  
- 尝试删除包含发送端口所使用的映射的 BizTalk 程序集。  
  
- 尝试删除包含不处于未登记状态或具有挂起实例的业务流程的 BizTalk 程序集。  
  
## <a name="usage"></a>用法  
 **BTSTask RemoveResource /ApplicationName:** *值* **/Luid:** *值*[**/Server:**<em>值</em>] [**/Database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|Description|  
|---------------|--------------|-----------------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|是|包含要删除的资源项目的 BizTalk 应用程序的名称。 如果名称包含空格，必须将其用双引号 （"）。|  
|**/ Luid** (或 **/L**，请参阅备注)|是|项目的本地唯一标识符 (LUID)。 可通过获得 LUID [ListApp 命令](../core/listapp-command.md)。|  
|**/ 服务器**(或 **/S**，请参阅备注)|“否”|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|“否”|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations，版本 = 1.0.0.0，区域性 = 中性，PublicKeyToken = 0123456789ABCDEF"**  
  
## <a name="remarks"></a>Remarks  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何从应用程序中删除项目](../core/how-to-remove-an-artifact-from-an-application.md)