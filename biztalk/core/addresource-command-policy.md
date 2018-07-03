---
title: AddResource 命令： 策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5effcbe-bf53-4741-8d5e-227620d4d84d
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43b90d74a177d11b478aff3302aa31306188cbcd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993654"
---
# <a name="addresource-command-policy"></a>AddResource 命令： 策略
若要将策略添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**system.biztalk: rules**类型参数。 运行此命令可将策略添加到 BizTalk 管理数据库中。 该策略还显示在 BizTalk Server 管理控制台中，显示位置为向其添加策略的应用程序的“策略”文件夹中。 此外，策略被列为使用时[ListApp 命令](../core/listapp-command.md)。  
  
 为了使此命令成功运行，该策略必须存在于规则引擎数据库中。 有关导入到规则引擎数据库中的策略的说明，请参阅[如何导入策略](../core/how-to-import-a-policy.md)。 使用 AddResource 命令添加策略时，还将自动添加该策略使用的所有词汇。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Rules** [**/overwrite**] **/Name:**<em>值</em>**/Version:**<em>值</em>[**/Server:**<em>值</em>] [**/Database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|“否”|向其添加策略的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.biztalk: rules** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/O**，请参阅备注)|“否”|更新现有策略的选项。 如果未指定，且应用程序中已经存在与要添加的策略名称相同的策略，则 AddResource 操作将失败。|  
|**/ 名称**(或 **/N**，请参阅备注)|是|策略的名称。|  
|**/Version** (或 **/V**，请参阅备注)|是|策略的版本号，格式为“数字.数字”。<br /><br /> 示例： 1.0|  
|**/ 服务器**(或 **/S**，请参阅备注)|“否”|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|“否”|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type: system.biztalk: rules / 覆盖 /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Remarks  
 如果已部署 MyPolicy，则上述命令将返回以下内容：  
  
 错误： 无法添加资源。  
  
 对 1 项资源的验证失败。  
  
 无法覆盖规则策略“MyPolicy”版本 1.0，因为它已用于生产环境中。  
  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何向应用程序添加策略](../core/how-to-add-a-policy-to-an-application.md)