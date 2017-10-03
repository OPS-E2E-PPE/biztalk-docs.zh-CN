---
title: "如何部署策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c4ab85a-5a6a-4153-90dc-52e099c0a62c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c3b07b0a8cebdd3322b49732ef4f32c04cbfede
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-policies"></a>如何部署策略
你可以通过使用以编程方式部署策略[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类**Microsoft.RuleEngine.RuleEngineExtensions**命名空间。 下面的示例代码演示如何使用[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类部署策略名为**LoanProcessing**:  
  
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
>  重载的构造函数的[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类采用作为参数对规则存储数据库的名称。 这使您能够将策略部署到 BizTalk Server 环境没有配置为使用的数据库中。  
  
## <a name="using-the-getdeploymentdriver-method"></a>使用 GetDeploymentDriver 方法  
 如果您要将策略部署到数据库，你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境配置为使用，则不需要创建**RuleSetDeploymentDriver**在代码中的对象。 相反，你可以在其中请求要创建的规则引擎**RuleSetDeploymentDriver**对象为你通过调用**GetDeploymentDriver**方法**配置**类在**System.RuleEngine**命名空间。 下面的示例代码演示如何调用**GetDeploymentDriver**方法：  
  
```  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.RuleEngine.Configuration.GetDeploymentDriver();  
```  
  
 **GetDeploymentDriver**方法检索的值**DeploymentDriverAssembly**和**DeploymentDriverClass**注册表项下**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**，并创建的实例**DeploymentDriverClass**。 下表显示这两个注册表项的默认值。  
  
|注册表项|值|  
|------------------|-----------|  
|DeploymentDriverAssembly|Microsoft.BizTalk.RuleEngineExtensions|  
|DeploymentDriverClass|Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver|  
  
 **RuleSetDeploymentDriver**类实现**IRuleSetDeploymentDriver**接口。 你可以通过创建一个类以实现开发自己的策略部署驱动程序**IRuleSetDeploymentDriver**接口并更改注册表项的值作为上述相应。