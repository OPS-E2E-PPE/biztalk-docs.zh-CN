---
title: AddResource 命令：策略 |Microsoft Docs
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
ms.openlocfilehash: a02a4e55ea2e6cac71882ebded5733bbad257889
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360524"
---
# <a name="addresource-command-policy"></a>AddResource 命令：策略
若要将策略添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**system.biztalk: rules**类型参数。 运行此命令可将策略添加到 BizTalk 管理数据库。 策略还显示在 BizTalk Server 管理控制台中，在应用程序添加到策略文件夹中。 此外，策略被列为使用时[ListApp 命令](../core/listapp-command.md)。  
  
 若要成功执行此命令，该策略必须存在的规则引擎数据库中。 有关导入到规则引擎数据库中的策略的说明，请参阅[如何导入策略](../core/how-to-import-a-policy.md)。 当使用 AddResource 命令添加一个策略时，请使用策略的所有词汇会自动都添加也。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Rules** [**/overwrite**] **/Name:**<em>值</em>**/Version:**<em>值</em>[**/Server:**<em>值</em>] [**/Database:**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|否|要将策略添加到 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.biztalk: rules** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/O**，请参阅备注)|否|若要更新现有策略的选项。 如果未指定，且策略已存在具有相同的名称作为要添加的策略的应用程序中，则 AddResource 操作将失败。|  
|**/ 名称**(或 **/N**，请参阅备注)|是|策略的名称。|  
|**/Version** (或 **/V**，请参阅备注)|是|在窗体 number.number 策略的版本号。<br /><br /> 例如：1.0|  
|**/ 服务器**(或 **/S**，请参阅备注)|否|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|否|BizTalk 管理数据库的名称。 如果未提供，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Rules  /Overwrite /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>备注  
 如果已部署 MyPolicy，上面的命令将返回以下：  
  
 错误：无法添加资源。  
  
 对 1 项资源的验证失败。  
  
 规则策略"MyPolicy"版本 1.0 无法被覆盖，因为它已在生产环境中。  
  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何向应用程序添加策略](../core/how-to-add-a-policy-to-an-application.md)