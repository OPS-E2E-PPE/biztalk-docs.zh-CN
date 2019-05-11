---
title: 替换公钥令牌实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Replace Public Key Token Utility
- utilities, Replace Public Key Token Utility
- public key token
ms.assetid: ed8673b9-af06-4bd7-b8b7-7371e4dd0fed
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5754f9ee853f1501d247f1236ca89d158b3788c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397900"
---
# <a name="replace-public-key-token-utility"></a><span data-ttu-id="d627c-102">替换公钥令牌实用工具</span><span class="sxs-lookup"><span data-stu-id="d627c-102">Replace Public Key Token Utility</span></span>
<span data-ttu-id="d627c-103">此实用程序可用于从强名称程序集密钥 (.snk) 文件派生公钥标记替换的公钥标记或变量的文件中。</span><span class="sxs-lookup"><span data-stu-id="d627c-103">This utility can be used to replace either a public key token or variable in a file with a public key token derived from a strong name assembly key (.snk) file.</span></span>  
  
 <span data-ttu-id="d627c-104">开发人员编写使用的脚本时，此实用程序可能很有用[BTSTask 命令行参考](../core/btstask-command-line-reference.md)部署的程序集。</span><span class="sxs-lookup"><span data-stu-id="d627c-104">This utility might be useful when a developer is writing a script that uses the [BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) to deploy an assembly.</span></span> <span data-ttu-id="d627c-105">有关部署成功完成，程序集的完全限定的名称必须提供，其中包括其公钥标记。</span><span class="sxs-lookup"><span data-stu-id="d627c-105">For the deployment to succeed, the fully qualified name of the assembly must be provided, which includes its public key token.</span></span> <span data-ttu-id="d627c-106">程序集的公钥标记是从.snk 文件中提取并在生成时分配给该程序集。</span><span class="sxs-lookup"><span data-stu-id="d627c-106">The public key token for an assembly is extracted from an .snk file and assigned to the assembly when it is built.</span></span> <span data-ttu-id="d627c-107">该程序集部署到新的环境之前，但是，它是通常使用重新生成其他公钥标记。</span><span class="sxs-lookup"><span data-stu-id="d627c-107">Before the assembly is deployed into a new environment, however, it is often rebuilt using a different public key token.</span></span> <span data-ttu-id="d627c-108">因此，开发人员可能不知道部署脚本运行时将程序集使用什么公钥标记。</span><span class="sxs-lookup"><span data-stu-id="d627c-108">As a result, the developer may not know what public key token will be used for the assembly when the deployment script is run.</span></span>  
  
 <span data-ttu-id="d627c-109">有两种方法，可以使用替换公钥标记实用程序来处理这种情况：</span><span class="sxs-lookup"><span data-stu-id="d627c-109">There are two ways that you can use the Replace Public Key Token utility to address this situation:</span></span>  
  
-   <span data-ttu-id="d627c-110">**方案 1。**</span><span class="sxs-lookup"><span data-stu-id="d627c-110">**Scenario 1.**</span></span> <span data-ttu-id="d627c-111">在部署脚本中，开发人员可以使用公钥标记或占位符表示公钥标记。</span><span class="sxs-lookup"><span data-stu-id="d627c-111">In the deployment script, the developer can use either a public key token or a placeholder representing the public key token.</span></span> <span data-ttu-id="d627c-112">之前运行脚本后，用户可以运行替换公钥标记实用程序从.snk 文件用于生成的程序集的目标环境中提取公钥标记替换公钥标记或脚本文件中的占位符。</span><span class="sxs-lookup"><span data-stu-id="d627c-112">Before running the script, a user can run the Replace Public Key Token utility to substitute the public key token or placeholder in the script file with the public key token extracted from the .snk file that was used to build the assembly for the destination environment.</span></span>  
  
-   <span data-ttu-id="d627c-113">**方案 2。**</span><span class="sxs-lookup"><span data-stu-id="d627c-113">**Scenario 2.**</span></span> <span data-ttu-id="d627c-114">开发人员可以配置为自动替代新公钥标记，按如下所示的脚本：在脚本开始时，调用替换公钥标记实用程序和指向包含公钥标记的.snk 文件。</span><span class="sxs-lookup"><span data-stu-id="d627c-114">The developer can configure the script to automatically substitute the new public key token, as follows: At the start of the script, invoke the Replace Public Key Token utility and point it to a .snk file that contains the public key token.</span></span> <span data-ttu-id="d627c-115">在脚本中，使用环境变量 %NEWTOKEN%表示公钥标记。</span><span class="sxs-lookup"><span data-stu-id="d627c-115">Within the script, use the environment variable %NEWTOKEN% to represent the public key token.</span></span> <span data-ttu-id="d627c-116">当脚本运行时，该实用程序从.snk 文件中提取公钥标记的值，并将其设置到环境变量 %NEWTOKEN%。</span><span class="sxs-lookup"><span data-stu-id="d627c-116">When the script runs, the utility extracts the value of the public key token from the .snk file and sets it into an environment variable %NEWTOKEN%.</span></span> <span data-ttu-id="d627c-117">当脚本运行时，%NEWTOKEN%的每个实例将用指定的.snk 文件中的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="d627c-117">When the script runs, each instance of %NEWTOKEN% will be with substituted with the public key token from the specified .snk file.</span></span> <span data-ttu-id="d627c-118">例如：</span><span class="sxs-lookup"><span data-stu-id="d627c-118">For example:</span></span>  
  
    ```  
    ReplacePKT.bat key.snk  
    ...  
    ...  
    gacutil /u Assembly, ... PublicKey=%NEWTOKEN% ...  
    ```  
  
## <a name="location-in-sdk"></a><span data-ttu-id="d627c-119">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="d627c-119">Location in SDK</span></span>  
 <span data-ttu-id="d627c-120">替换公钥标记实用程序位于：</span><span class="sxs-lookup"><span data-stu-id="d627c-120">The Replace Public Key Token utility is located in:</span></span>  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="d627c-121">SDK\Utilities\ReplacePublicKeyToken\\。</span><span class="sxs-lookup"><span data-stu-id="d627c-121">SDK\Utilities\ReplacePublicKeyToken\\.</span></span>  
  
 <span data-ttu-id="d627c-122">替换公钥标记实用程序包括三个文件：</span><span class="sxs-lookup"><span data-stu-id="d627c-122">The Replace Public Key Token utility comprises three files:</span></span>  
  
-   <span data-ttu-id="d627c-123">ReplacePKT.bat</span><span class="sxs-lookup"><span data-stu-id="d627c-123">ReplacePKT.bat</span></span>  
  
-   <span data-ttu-id="d627c-124">ReplacePKT.vbs</span><span class="sxs-lookup"><span data-stu-id="d627c-124">ReplacePKT.vbs</span></span>  
  
-   <span data-ttu-id="d627c-125">ReplacePKT.wsf</span><span class="sxs-lookup"><span data-stu-id="d627c-125">ReplacePKT.wsf</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d627c-126">过程</span><span class="sxs-lookup"><span data-stu-id="d627c-126">Procedures</span></span>  
 <span data-ttu-id="d627c-127">使用以下过程在方案 1 中所述，使用从.snk 文件中提取公钥标记替换公钥标记或占位符文件中的所有实例。</span><span class="sxs-lookup"><span data-stu-id="d627c-127">Use the following procedure to replace all instances of a public key token or a placeholder in a file with a public key token extracted from an .snk file, as described in Scenario 1.</span></span>  
  
#### <a name="to-replace-instances-of-a-public-key-token-or-a-placeholder-in-a-file"></a><span data-ttu-id="d627c-128">替换公钥标记或占位符文件中的实例</span><span class="sxs-lookup"><span data-stu-id="d627c-128">To replace instances of a public key token or a placeholder in a file</span></span>  
  
1. <span data-ttu-id="d627c-129">请确保三个替换公钥标记实用程序文件 （ReplacePKT.bat、 ReplacePKT.vbs、 ReplacePKT.wsf）、 脚本文件和.snk 文件可从本地计算机。</span><span class="sxs-lookup"><span data-stu-id="d627c-129">Make sure that the three Replace Public Key Token utility files (ReplacePKT.bat, ReplacePKT.vbs, ReplacePKT.wsf), the script file, and the .snk file are all available from the local computer.</span></span>  
  
2. <span data-ttu-id="d627c-130">在命令窗口中，将目录更改到包含替换公钥标记实用程序文件的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d627c-130">In a command window, change the directory to the folder containing the Replace Public Key utility files.</span></span>  
  
3. <span data-ttu-id="d627c-131">从命令提示符处，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d627c-131">From a command prompt, run the following command:</span></span>  
  
4. <span data-ttu-id="d627c-132">**ReplacePKT \<**  *.snk 文件* **\> \<** *旧公钥标记* **\>\<** *文件替换* **\>**</span><span class="sxs-lookup"><span data-stu-id="d627c-132">**ReplacePKT \<** *.snk file* **\> \<** *old public key token* **\> \<** *file to replace* **\>**</span></span>  
  
   |<span data-ttu-id="d627c-133">Option</span><span class="sxs-lookup"><span data-stu-id="d627c-133">Option</span></span>|<span data-ttu-id="d627c-134">Description</span><span class="sxs-lookup"><span data-stu-id="d627c-134">Description</span></span>|  
   |------------|-----------------|  
   |<span data-ttu-id="d627c-135">**\<** *.snk 文件* **\>**</span><span class="sxs-lookup"><span data-stu-id="d627c-135">**\<** *.snk file* **\>**</span></span>|<span data-ttu-id="d627c-136">包含所需的公钥标记的.snk 文件的完整路径替换现有的公钥标记或占位符。</span><span class="sxs-lookup"><span data-stu-id="d627c-136">Full path of the .snk file containing the public key token that you want substitute for the existing public key token or placeholder.</span></span>|  
   |<span data-ttu-id="d627c-137">**\<** *旧公钥标记* **\>**</span><span class="sxs-lookup"><span data-stu-id="d627c-137">**\<** *old public key token* **\>**</span></span>|<span data-ttu-id="d627c-138">公钥标记或您要替换的占位符。</span><span class="sxs-lookup"><span data-stu-id="d627c-138">Public key token or placeholder that you want to replace.</span></span>|  
   |<span data-ttu-id="d627c-139">**\<** *若要替换的文件* **\>**</span><span class="sxs-lookup"><span data-stu-id="d627c-139">**\<** *file to replace* **\>**</span></span>|<span data-ttu-id="d627c-140">想要替换的公钥标记或占位符的文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="d627c-140">Full path of the file in which you want to replace the public key token or placeholder.</span></span>|  
  
    <span data-ttu-id="d627c-141">例如：</span><span class="sxs-lookup"><span data-stu-id="d627c-141">Example:</span></span>  
  
    <span data-ttu-id="d627c-142">**ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**</span><span class="sxs-lookup"><span data-stu-id="d627c-142">**ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**</span></span>  
  
   <span data-ttu-id="d627c-143">使用以下过程中使用从.snk 文件派生的公钥标记，如方案 2 中所述的脚本自动设置环境变量。</span><span class="sxs-lookup"><span data-stu-id="d627c-143">Use the following procedure to automatically set an environment variable in a script that uses a public key token derived from an .snk file, as described in Scenario 2.</span></span>  
  
#### <a name="to-set-an-environment-variable-that-uses-a-public-key-token"></a><span data-ttu-id="d627c-144">若要设置使用公钥标记的环境变量</span><span class="sxs-lookup"><span data-stu-id="d627c-144">To set an environment variable that uses a public key token</span></span>  
  
1.  <span data-ttu-id="d627c-145">在脚本文件的开头，添加以下代码行：</span><span class="sxs-lookup"><span data-stu-id="d627c-145">At the beginning of your script file, add the following line of code:</span></span>  
  
    ```  
    ReplacePKT <filename>.snk  
    ```  
  
     <span data-ttu-id="d627c-146">其中\<*文件名*\>是从中派生公钥标记的.snk 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d627c-146">Where \<*filename*\> is the name of the .snk file from which to derive the public key token.</span></span>  
  
    ```  
    Example: ReplacePKT.bat MyToken.snk  
    ```  
  
2.  <span data-ttu-id="d627c-147">在脚本文件中，使用`%NEWTOKEN%`来表示公钥标记。</span><span class="sxs-lookup"><span data-stu-id="d627c-147">In your script file, use `%NEWTOKEN%` to represent the public key token.</span></span>  
  
     <span data-ttu-id="d627c-148">例如：</span><span class="sxs-lookup"><span data-stu-id="d627c-148">Example:</span></span>  
  
    ```  
    PublicKey=%NEWTOKEN%  
    ```  
  
3.  <span data-ttu-id="d627c-149">当向用户提供脚本文件时，包括组成替换公钥标记实用程序 （ReplacePKT.bat、 ReplacePKT.vbs、 ReplacePKT.wsf） 的三个文件。</span><span class="sxs-lookup"><span data-stu-id="d627c-149">When you deliver your script file to your users, include the three files that comprise the Replace Public Key Token utility (ReplacePKT.bat, ReplacePKT.vbs, ReplacePKT.wsf).</span></span> <span data-ttu-id="d627c-150">请确保，您的脚本的用户的所有文件之前复制到文件系统上的相同文件夹运行您的脚本。</span><span class="sxs-lookup"><span data-stu-id="d627c-150">Make sure that users of your script copy all of the files to the same folder on the file system before running your script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d627c-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="d627c-151">See Also</span></span>  
 [<span data-ttu-id="d627c-152">SDK 中的实用工具</span><span class="sxs-lookup"><span data-stu-id="d627c-152">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)