---
title: 如何部署策略 |Microsoft 文档
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
ms.openlocfilehash: 1c3b07b0a8cebdd3322b49732ef4f32c04cbfede
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249181"
---
# <a name="how-to-deploy-policies"></a><span data-ttu-id="881a8-102">如何部署策略</span><span class="sxs-lookup"><span data-stu-id="881a8-102">How to Deploy Policies</span></span>
<span data-ttu-id="881a8-103">你可以通过使用以编程方式部署策略[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类**Microsoft.RuleEngine.RuleEngineExtensions**命名空间。</span><span class="sxs-lookup"><span data-stu-id="881a8-103">You can deploy policies programmatically by using the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class in the **Microsoft.RuleEngine.RuleEngineExtensions** namespace.</span></span> <span data-ttu-id="881a8-104">下面的示例代码演示如何使用[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类部署策略名为**LoanProcessing**:</span><span class="sxs-lookup"><span data-stu-id="881a8-104">The following sample code demonstrates how to use the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class to deploy a policy named **LoanProcessing**:</span></span>  
  
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
>  <span data-ttu-id="881a8-105">重载的构造函数的[Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx)类采用作为参数对规则存储数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="881a8-105">The overloaded constructors of the [Microsoft.RuleEngine.RuleSetDeploymentDriver](http://msdn.microsoft.com/library/microsoft.ruleengine.rulesetdeploymentdriver.aspx) class take the names of the rule store database as a parameter.</span></span> <span data-ttu-id="881a8-106">这使您能够将策略部署到 BizTalk Server 环境没有配置为使用的数据库中。</span><span class="sxs-lookup"><span data-stu-id="881a8-106">This allows you to deploy policies to a database that your BizTalk Server environment is not configured to use.</span></span>  
  
## <a name="using-the-getdeploymentdriver-method"></a><span data-ttu-id="881a8-107">使用 GetDeploymentDriver 方法</span><span class="sxs-lookup"><span data-stu-id="881a8-107">Using the GetDeploymentDriver Method</span></span>  
 <span data-ttu-id="881a8-108">如果您要将策略部署到数据库，你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境配置为使用，则不需要创建**RuleSetDeploymentDriver**在代码中的对象。</span><span class="sxs-lookup"><span data-stu-id="881a8-108">If you are deploying policies to the database that your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is configured to use, you do not have to create the **RuleSetDeploymentDriver** object in the code.</span></span> <span data-ttu-id="881a8-109">相反，你可以在其中请求要创建的规则引擎**RuleSetDeploymentDriver**对象为你通过调用**GetDeploymentDriver**方法**配置**类在**System.RuleEngine**命名空间。</span><span class="sxs-lookup"><span data-stu-id="881a8-109">Instead, you can request the rule engine to create a **RuleSetDeploymentDriver** object for you by invoking the **GetDeploymentDriver** method of the **Configuration** class in the **System.RuleEngine** namespace.</span></span> <span data-ttu-id="881a8-110">下面的示例代码演示如何调用**GetDeploymentDriver**方法：</span><span class="sxs-lookup"><span data-stu-id="881a8-110">The following sample code demonstrates how to invoke the **GetDeploymentDriver** method:</span></span>  
  
```  
Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
dd = new Microsoft.RuleEngine.Configuration.GetDeploymentDriver();  
```  
  
 <span data-ttu-id="881a8-111">**GetDeploymentDriver**方法检索的值**DeploymentDriverAssembly**和**DeploymentDriverClass**注册表项下**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**，并创建的实例**DeploymentDriverClass**。</span><span class="sxs-lookup"><span data-stu-id="881a8-111">The **GetDeploymentDriver** method retrieves the values of the **DeploymentDriverAssembly** and **DeploymentDriverClass** registry keys under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, and creates an instance of **DeploymentDriverClass**.</span></span> <span data-ttu-id="881a8-112">下表显示这两个注册表项的默认值。</span><span class="sxs-lookup"><span data-stu-id="881a8-112">The following table shows the default values of these two registry keys.</span></span>  
  
|<span data-ttu-id="881a8-113">注册表项</span><span class="sxs-lookup"><span data-stu-id="881a8-113">Registry key</span></span>|<span data-ttu-id="881a8-114">值</span><span class="sxs-lookup"><span data-stu-id="881a8-114">Value</span></span>|  
|------------------|-----------|  
|<span data-ttu-id="881a8-115">DeploymentDriverAssembly</span><span class="sxs-lookup"><span data-stu-id="881a8-115">DeploymentDriverAssembly</span></span>|<span data-ttu-id="881a8-116">Microsoft.BizTalk.RuleEngineExtensions</span><span class="sxs-lookup"><span data-stu-id="881a8-116">Microsoft.BizTalk.RuleEngineExtensions</span></span>|  
|<span data-ttu-id="881a8-117">DeploymentDriverClass</span><span class="sxs-lookup"><span data-stu-id="881a8-117">DeploymentDriverClass</span></span>|<span data-ttu-id="881a8-118">Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver</span><span class="sxs-lookup"><span data-stu-id="881a8-118">Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver</span></span>|  
  
 <span data-ttu-id="881a8-119">**RuleSetDeploymentDriver**类实现**IRuleSetDeploymentDriver**接口。</span><span class="sxs-lookup"><span data-stu-id="881a8-119">The **RuleSetDeploymentDriver** class implements the **IRuleSetDeploymentDriver** interface.</span></span> <span data-ttu-id="881a8-120">你可以通过创建一个类以实现开发自己的策略部署驱动程序**IRuleSetDeploymentDriver**接口并更改注册表项的值作为上述相应。</span><span class="sxs-lookup"><span data-stu-id="881a8-120">You can develop your own policy deployment driver by creating a class that implements the **IRuleSetDeploymentDriver** interface and change the values for the registry keys described above as appropriate.</span></span>