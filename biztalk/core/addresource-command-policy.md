---
title: AddResource 命令： 策略 |Microsoft 文档
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
ms.openlocfilehash: 9037e2277823027f1d379b8a65552b4d32ac05a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230509"
---
# <a name="addresource-command-policy"></a>AddResource 命令： 策略
若要将策略添加到 BizTalk 应用程序，请使用**AddResource**命令并指定**System.BizTalk:Rules**为类型参数。 运行此命令可将策略添加到 BizTalk 管理数据库中。 该策略还显示在 BizTalk Server 管理控制台中，显示位置为向其添加策略的应用程序的“策略”文件夹中。 此外，将列出的策略，当你使用[ListApp 命令](../core/listapp-command.md)。  
  
 为了使此命令成功运行，该策略必须存在于规则引擎数据库中。 有关将策略导入规则引擎数据库的说明，请参阅[如何导入策略](../core/how-to-import-a-policy.md)。 使用 AddResource 命令添加策略时，还将自动添加该策略使用的所有词汇。  
  
## <a name="usage"></a>用法  
 **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:Rules** [**/覆盖**]**Name:***值***/Version:***值*[**/Server:** *值*] [**/数据库：***值*]  
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|是|向其添加策略的 BizTalk 应用程序的名称。 如果名称包含空格，必须将它括在双引号 （"）。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。|  
|**/ 键入**(或 **/T**，请参阅备注)|是|**System.BizTalk:Rules** （此值不区分大小写。）|  
|**/ 覆盖**(或 **/O**，请参阅备注)|是|更新现有策略的选项。 如果未指定，且应用程序中已经存在与要添加的策略名称相同的策略，则 AddResource 操作将失败。|  
|**/ 名称**(或 **/N**，请参阅备注)|是|策略的名称。|  
|**/ 版本**(或 **/V**，请参阅备注)|是|策略的版本号，格式为“数字.数字”。<br /><br /> 示例： 1.0|  
|**/ 服务器**(或 **/S**，请参阅备注)|是|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
|**/ 数据库**(或 **/D**，请参阅备注)|是|BizTalk 管理数据库的名称。 如果未提供，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="sample"></a>示例  
 **BTSTask AddResource /ApplicationName:MyApplication /Type: System.BizTalk:Rules / 覆盖 /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>注释  
 如果已部署 MyPolicy，则上述命令将返回以下内容：  
  
 错误： 无法添加资源。  
  
 对 1 项资源的验证失败。  
  
 无法覆盖规则策略“MyPolicy”版本 1.0，因为它已用于生产环境中。  
  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [AddResource 命令](../core/addresource-command.md)   
 [如何将策略添加到应用程序](../core/how-to-add-a-policy-to-an-application.md)