---
title: 如何部署策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c4ab85a-5a6a-4153-90dc-52e099c0a62c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d318437c6ddb62b52599ce6da51022775ad1fcd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338637"
---
# <a name="how-to-deploy-policies"></a>如何部署策略
您可以通过使用以编程方式部署策略[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类**Microsoft.RuleEngine.RuleEngineExtensions**命名空间。 下面的示例代码演示如何使用[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类来部署一个名为策略**LoanProcessing**:  
  
```  
string policyName = “LoanProcessing”;  
int majorRev = Convert.ToInt16(args[1]);  
int minorRev = Convert.ToInt16(args[2]);  
RuleSetInfo rsi = new RuleSetInfo(policyName,majorRev,minorRev);  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
dd.Deploy(rsi);  
```  
  
> [!NOTE]
>  重载构造函数[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类接受作为参数将规则存储数据库的名称。 这使您可以将策略部署到的数据库，BizTalk Server 环境未配置为使用。  
  
## <a name="using-the-getdeploymentdriver-method"></a>使用 GetDeploymentDriver 方法  
 如果要将策略部署到数据库，你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境配置为使用，不需要创建**RuleSetDeploymentDriver**在代码中的对象。 相反，你可以在其中请求要创建的规则引擎**RuleSetDeploymentDriver**对象，通过调用**GetDeploymentDriver**方法**配置**类中**System.RuleEngine**命名空间。 下面的示例代码演示如何调用**GetDeploymentDriver**方法：  
  
```  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.RuleEngine.Configuration.GetDeploymentDriver();  
```  
  
 **GetDeploymentDriver**方法检索的值**DeploymentDriverAssembly**并**DeploymentDriverClass**注册表项下**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**，并创建的实例**DeploymentDriverClass**。 下表显示了这些两个注册表项默认值。  
  
|注册表项|ReplTest1|  
|------------------|-----------|  
|DeploymentDriverAssembly|Microsoft.BizTalk.RuleEngineExtensions|  
|DeploymentDriverClass|Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver|  
  
 **RuleSetDeploymentDriver**类实现**IRuleSetDeploymentDriver**接口。 可以通过创建实现的类开发您自己的策略部署驱动程序**IRuleSetDeploymentDriver**适当的接口和注册表项的值作为上述的更改。