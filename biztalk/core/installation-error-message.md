---
title: 安装错误消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation, error message
- error messages, installation
ms.assetid: 593b033f-03da-43ae-a948-f87aa5e4bccd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2513ed65a332839cf1cbeef1b64e99c169b66ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382177"
---
# <a name="installation-error-message"></a><span data-ttu-id="44676-102">安装错误消息</span><span class="sxs-lookup"><span data-stu-id="44676-102">Installation Error Message</span></span>
<span data-ttu-id="44676-103">安装 Microsoft BizTalk Adapter for TIBCO Enterprise Message Service，定义发送或接收后它的位置可能会导致以下错误：</span><span class="sxs-lookup"><span data-stu-id="44676-103">After you install Microsoft BizTalk Adapter for TIBCO Enterprise Message Service, defining a send or receive location for it might result in the following error:</span></span>  
  
 <span data-ttu-id="44676-104">消息引擎未能添加接收 URL"\<发送/接收位置 URL\>"到"TIBCO EMS"适配器。</span><span class="sxs-lookup"><span data-stu-id="44676-104">The Messaging Engine failed to add a receive URL "\< send/receive location URL\>" to the adapter "TIBCO EMS".</span></span> <span data-ttu-id="44676-105">原因:"文件或程序集名称 TIBCO。EMS 或其某个依赖项，未找到。"</span><span class="sxs-lookup"><span data-stu-id="44676-105">Reason: "File or assembly name TIBCO.EMS, or one of its dependencies, was not found."</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="44676-106">可能的原因</span><span class="sxs-lookup"><span data-stu-id="44676-106">Possible Causes</span></span>  
 <span data-ttu-id="44676-107">此错误通常有以下原因之一。</span><span class="sxs-lookup"><span data-stu-id="44676-107">This error usually has one of the following causes.</span></span>  
  
### <a name="assembly-not-in-gac"></a><span data-ttu-id="44676-108">不在 GAC 中的程序集</span><span class="sxs-lookup"><span data-stu-id="44676-108">Assembly Not in GAC</span></span>  
 <span data-ttu-id="44676-109">用于 TIBCO EMS 的 BizTalk 适配器是.NET Framework 应用程序，并使用.NET Framework 程序集，TIBCO。EMS。</span><span class="sxs-lookup"><span data-stu-id="44676-109">BizTalk Adapter for TIBCO EMS is a .NET Framework application, and uses the .NET Framework assembly, TIBCO.EMS.</span></span> <span data-ttu-id="44676-110">此程序集必须在.NET Framework 在运行时查找.NET Framework 全局程序集缓存 (GAC) 中存在。</span><span class="sxs-lookup"><span data-stu-id="44676-110">This assembly must be present in the .NET Framework global assembly cache (GAC) for the .NET Framework to find it at run time.</span></span>  
  
#### <a name="solution"></a><span data-ttu-id="44676-111">解决方案</span><span class="sxs-lookup"><span data-stu-id="44676-111">Solution</span></span>  
 <span data-ttu-id="44676-112">若要确定程序集是否位于 GAC 中，打开命令提示符并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="44676-112">To determine if the assembly is present in the GAC, open a command prompt and type the following command:</span></span>  
  
 `GACUTIL /L TIBCO.EMS`  
  
 <span data-ttu-id="44676-113">如果结果未显示任何项，则必须向 GAC 添加程序集。</span><span class="sxs-lookup"><span data-stu-id="44676-113">If the result shows zero items, you must add the assembly to the GAC.</span></span> <span data-ttu-id="44676-114">若要执行此操作，打开命令提示符，将目录更改为 TIBCO EMS 安装 clients\cs 目录 （默认安装位置为 C:\TIBCO\EMS\Clients\CS），并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="44676-114">To do this, open a command prompt, change directories to your TIBCO EMS installation clients\cs directory (the default installation location is C:\TIBCO\EMS\Clients\CS), and run the following command:</span></span>  
  
 `GACUTIL /i TIBCO.EMS.DLL`  
  
### <a name="different-version-of-assembly-in-gac"></a><span data-ttu-id="44676-115">不同版本的 GAC 中程序集</span><span class="sxs-lookup"><span data-stu-id="44676-115">Different Version of Assembly in GAC</span></span>  
 <span data-ttu-id="44676-116">TIBCO。EMS.dll 程序集位于 gac 中，但它是与构建 TIBCO EMS 的 BizTalk 适配器时使用不同的版本。</span><span class="sxs-lookup"><span data-stu-id="44676-116">The TIBCO.EMS.dll assembly is in the GAC, but it is a different version from the one used to build BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="44676-117">如果 TIBCO。在计算机安装的 EMS.dll 是从产品版本 4.2 或更高版本，它应与用于生成的适配器 （您可以验证该信息与 TIBCO） 的版本兼容。</span><span class="sxs-lookup"><span data-stu-id="44676-117">If the TIBCO.EMS.dll that is installed on the computer is from a product version 4.2 or above, it should be compatible with the version used to build the adapter (you can verify that information with TIBCO).</span></span>  
  
#### <a name="solution"></a><span data-ttu-id="44676-118">解决方案</span><span class="sxs-lookup"><span data-stu-id="44676-118">Solution</span></span>  
 <span data-ttu-id="44676-119">.NET Framework 提供了一种方法，若要解决此问题。</span><span class="sxs-lookup"><span data-stu-id="44676-119">The .NET Framework provides a way to work around this problem.</span></span> <span data-ttu-id="44676-120">它称为*绑定重定向*，它使用配置文件。</span><span class="sxs-lookup"><span data-stu-id="44676-120">It is called *binding redirection*, which uses a configuration file.</span></span>  
  
 <span data-ttu-id="44676-121">请执行以下步骤来消除此错误消息：</span><span class="sxs-lookup"><span data-stu-id="44676-121">Follow these steps to eliminate the error message:</span></span>  
  
1. <span data-ttu-id="44676-122">使用任何文本编辑器打开 BTSNTSVC.exe.config 文件。</span><span class="sxs-lookup"><span data-stu-id="44676-122">With any text editor, open the file BTSNTSVC.exe.config.</span></span>  
  
    <span data-ttu-id="44676-123">该文件位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]目录 (默认安装位置是： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="44676-123">The file is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directory (the default installation location is: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]).</span></span>  
  
2. <span data-ttu-id="44676-124">将以下条目添加到 BTSNTSVC.exe.config 文件中，为的子\<assemblyBinding\>元素：</span><span class="sxs-lookup"><span data-stu-id="44676-124">Add the following entry to the BTSNTSVC.exe.config file, as a child of the \<assemblyBinding\> element:</span></span>  
  
```  
<dependentAssembly>  
    <assemblyIdentity name='TIBCO.EMS'  
        publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
    <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
        newVersion='1.0.0.0' />  
</dependentAssembly>  
```  
  
 <span data-ttu-id="44676-125">如果先前已修改 BTSNTSVC.exe.config 文件， \<assemblyBinding\>元素不应如下所示：</span><span class="sxs-lookup"><span data-stu-id="44676-125">If the BTSNTSVC.exe.config file has not been previously modified, the \<assemblyBinding\> element would not look like this:</span></span>  
  
```  
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
    <probing privatePath="BizTalk Assemblies;Developer  
        Tools;Tracking;Tracking\interop" />  
    <dependentAssembly>  
        <assemblyIdentity name='TIBCO.EMS'  
            publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
        <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
            newVersion='1.0.0.0' />  
    </dependentAssembly>  
</assemblyBinding>  
```  
  
1. <span data-ttu-id="44676-126">在命令提示符下键入命令： `GACUTIL /L TIBCO.EMS`。</span><span class="sxs-lookup"><span data-stu-id="44676-126">In a command prompt, type the command: `GACUTIL /L TIBCO.EMS`.</span></span>  
  
2. <span data-ttu-id="44676-127">将复制 TIBCO。EMS 输出中的程序集版本数。</span><span class="sxs-lookup"><span data-stu-id="44676-127">Copy the TIBCO.EMS assembly version number from the output.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="44676-128">显示两个版本号： 一个是 gacutil 实用工具的版本号。</span><span class="sxs-lookup"><span data-stu-id="44676-128">Two version numbers appear: one is the version number of the gacutil utility.</span></span> <span data-ttu-id="44676-129">所需的第二个的版本号，之后将显示**版本 =**。</span><span class="sxs-lookup"><span data-stu-id="44676-129">You want the second version number, which appears just after **Version=**.</span></span>  
  
3. <span data-ttu-id="44676-130">之后粘贴之间引号中，BTSNTSVC.exe.config 文件中的版本号**newVersion =** （以粗体显示上一 XML 示例中的字符）。</span><span class="sxs-lookup"><span data-stu-id="44676-130">Paste the version number in the BTSNTSVC.exe.config file, between the quotation marks, right after **newVersion=** (bold characters in the previous XML example).</span></span>  
  
4. <span data-ttu-id="44676-131">保存修改后的 BTSNTSVC.exe.config 文件。</span><span class="sxs-lookup"><span data-stu-id="44676-131">Save the modified BTSNTSVC.exe.config file.</span></span>  
  
5. <span data-ttu-id="44676-132">重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机。</span><span class="sxs-lookup"><span data-stu-id="44676-132">Restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44676-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="44676-133">See Also</span></span>  
 [<span data-ttu-id="44676-134">TIBCO Enterprise Message Service 的疑难解答</span><span class="sxs-lookup"><span data-stu-id="44676-134">Troubleshooting TIBCO Enterprise Message Service</span></span>](../core/troubleshooting-tibco-enterprise-message-service.md)