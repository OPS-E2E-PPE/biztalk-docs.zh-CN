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
# <a name="how-to-deploy-policies"></a><span data-ttu-id="65a0a-102">如何部署策略</span><span class="sxs-lookup"><span data-stu-id="65a0a-102">How to Deploy Policies</span></span>
<span data-ttu-id="65a0a-103">您可以通过使用以编程方式部署策略[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类**Microsoft.RuleEngine.RuleEngineExtensions**命名空间。</span><span class="sxs-lookup"><span data-stu-id="65a0a-103">You can deploy policies programmatically by using the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class in the **Microsoft.RuleEngine.RuleEngineExtensions** namespace.</span></span> <span data-ttu-id="65a0a-104">下面的示例代码演示如何使用[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类来部署一个名为策略**LoanProcessing**:</span><span class="sxs-lookup"><span data-stu-id="65a0a-104">The following sample code demonstrates how to use the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class to deploy a policy named **LoanProcessing**:</span></span>  
  
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
>  <span data-ttu-id="65a0a-105">重载构造函数[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类接受作为参数将规则存储数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="65a0a-105">The overloaded constructors of the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class take the names of the rule store database as a parameter.</span></span> <span data-ttu-id="65a0a-106">这使您可以将策略部署到的数据库，BizTalk Server 环境未配置为使用。</span><span class="sxs-lookup"><span data-stu-id="65a0a-106">This allows you to deploy policies to a database that your BizTalk Server environment is not configured to use.</span></span>  
  
## <a name="using-the-getdeploymentdriver-method"></a><span data-ttu-id="65a0a-107">使用 GetDeploymentDriver 方法</span><span class="sxs-lookup"><span data-stu-id="65a0a-107">Using the GetDeploymentDriver Method</span></span>  
 <span data-ttu-id="65a0a-108">如果要将策略部署到数据库，你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境配置为使用，不需要创建**RuleSetDeploymentDriver**在代码中的对象。</span><span class="sxs-lookup"><span data-stu-id="65a0a-108">If you are deploying policies to the database that your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is configured to use, you do not have to create the **RuleSetDeploymentDriver** object in the code.</span></span> <span data-ttu-id="65a0a-109">相反，你可以在其中请求要创建的规则引擎**RuleSetDeploymentDriver**对象，通过调用**GetDeploymentDriver**方法**配置**类中**System.RuleEngine**命名空间。</span><span class="sxs-lookup"><span data-stu-id="65a0a-109">Instead, you can request the rule engine to create a **RuleSetDeploymentDriver** object for you by invoking the **GetDeploymentDriver** method of the **Configuration** class in the **System.RuleEngine** namespace.</span></span> <span data-ttu-id="65a0a-110">下面的示例代码演示如何调用**GetDeploymentDriver**方法：</span><span class="sxs-lookup"><span data-stu-id="65a0a-110">The following sample code demonstrates how to invoke the **GetDeploymentDriver** method:</span></span>  
  
```  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.RuleEngine.Configuration.GetDeploymentDriver();  
```  
  
 <span data-ttu-id="65a0a-111">**GetDeploymentDriver**方法检索的值**DeploymentDriverAssembly**并**DeploymentDriverClass**注册表项下**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**，并创建的实例**DeploymentDriverClass**。</span><span class="sxs-lookup"><span data-stu-id="65a0a-111">The **GetDeploymentDriver** method retrieves the values of the **DeploymentDriverAssembly** and **DeploymentDriverClass** registry keys under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, and creates an instance of **DeploymentDriverClass**.</span></span> <span data-ttu-id="65a0a-112">下表显示了这些两个注册表项默认值。</span><span class="sxs-lookup"><span data-stu-id="65a0a-112">The following table shows the default values of these two registry keys.</span></span>  
  
|<span data-ttu-id="65a0a-113">注册表项</span><span class="sxs-lookup"><span data-stu-id="65a0a-113">Registry key</span></span>|<span data-ttu-id="65a0a-114">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="65a0a-114">Value</span></span>|  
|------------------|-----------|  
|<span data-ttu-id="65a0a-115">DeploymentDriverAssembly</span><span class="sxs-lookup"><span data-stu-id="65a0a-115">DeploymentDriverAssembly</span></span>|<span data-ttu-id="65a0a-116">Microsoft.BizTalk.RuleEngineExtensions</span><span class="sxs-lookup"><span data-stu-id="65a0a-116">Microsoft.BizTalk.RuleEngineExtensions</span></span>|  
|<span data-ttu-id="65a0a-117">DeploymentDriverClass</span><span class="sxs-lookup"><span data-stu-id="65a0a-117">DeploymentDriverClass</span></span>|<span data-ttu-id="65a0a-118">Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver</span><span class="sxs-lookup"><span data-stu-id="65a0a-118">Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver</span></span>|  
  
 <span data-ttu-id="65a0a-119">**RuleSetDeploymentDriver**类实现**IRuleSetDeploymentDriver**接口。</span><span class="sxs-lookup"><span data-stu-id="65a0a-119">The **RuleSetDeploymentDriver** class implements the **IRuleSetDeploymentDriver** interface.</span></span> <span data-ttu-id="65a0a-120">可以通过创建实现的类开发您自己的策略部署驱动程序**IRuleSetDeploymentDriver**适当的接口和注册表项的值作为上述的更改。</span><span class="sxs-lookup"><span data-stu-id="65a0a-120">You can develop your own policy deployment driver by creating a class that implements the **IRuleSetDeploymentDriver** interface and change the values for the registry keys described above as appropriate.</span></span>