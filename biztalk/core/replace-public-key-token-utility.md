---
title: "将公共密钥令牌实用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Replace Public Key Token Utility
- utilities, Replace Public Key Token Utility
- public key token
ms.assetid: ed8673b9-af06-4bd7-b8b7-7371e4dd0fed
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dee6fff7de065c3663ab373f739f7fb465947c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="replace-public-key-token-utility"></a><span data-ttu-id="a9ecb-102">将公共密钥令牌实用程序</span><span class="sxs-lookup"><span data-stu-id="a9ecb-102">Replace Public Key Token Utility</span></span>
<span data-ttu-id="a9ecb-103">此实用程序可以用从强名称程序集密钥 (.snk) 文件派生的公钥标记替换文件中的公钥标记或变量。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-103">This utility can be used to replace either a public key token or variable in a file with a public key token derived from a strong name assembly key (.snk) file.</span></span>  
  
 <span data-ttu-id="a9ecb-104">此实用程序可能会很有用，开发人员编写的脚本使用时[BTSTask 命令行参考](../core/btstask-command-line-reference.md)部署程序集。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-104">This utility might be useful when a developer is writing a script that uses the [BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) to deploy an assembly.</span></span> <span data-ttu-id="a9ecb-105">要想成功部署，必须提供程序集的完全限定名称，包括程序集的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-105">For the deployment to succeed, the fully qualified name of the assembly must be provided, which includes its public key token.</span></span> <span data-ttu-id="a9ecb-106">程序集的公钥标记是从 .snk 文件中提取的，并在程序集生成时指定给它。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-106">The public key token for an assembly is extracted from an .snk file and assigned to the assembly when it is built.</span></span> <span data-ttu-id="a9ecb-107">然而，在将程序集部署到新的环境之前，通常会使用其他公钥标记重新生成它。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-107">Before the assembly is deployed into a new environment, however, it is often rebuilt using a different public key token.</span></span> <span data-ttu-id="a9ecb-108">因此，开发人员可能不知道部署脚本运行时程序集将使用什么公钥标记。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-108">As a result, the developer may not know what public key token will be used for the assembly when the deployment script is run.</span></span>  
  
 <span data-ttu-id="a9ecb-109">可以通过以下两种方法使用替换公钥标记实用程序解决此问题：</span><span class="sxs-lookup"><span data-stu-id="a9ecb-109">There are two ways that you can use the Replace Public Key Token utility to address this situation:</span></span>  
  
-   <span data-ttu-id="a9ecb-110">**方案 1。**</span><span class="sxs-lookup"><span data-stu-id="a9ecb-110">**Scenario 1.**</span></span> <span data-ttu-id="a9ecb-111">在部署脚本中，开发人员可以使用公钥标记，也可以使用表示公钥标记的占位符。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-111">In the deployment script, the developer can use either a public key token or a placeholder representing the public key token.</span></span> <span data-ttu-id="a9ecb-112">运行脚本之前，用户可以运行替换公钥标记实用程序，以使用从 .snk 文件（用于针对目标环境生成程序集的文件）提取的公钥标记替代脚本文件中的公钥标记或占位符。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-112">Before running the script, a user can run the Replace Public Key Token utility to substitute the public key token or placeholder in the script file with the public key token extracted from the .snk file that was used to build the assembly for the destination environment.</span></span>  
  
-   <span data-ttu-id="a9ecb-113">**方案 2。**</span><span class="sxs-lookup"><span data-stu-id="a9ecb-113">**Scenario 2.**</span></span> <span data-ttu-id="a9ecb-114">开发人员可以配置用于自动替换新公钥标记，如下所示的脚本： 脚本开始时，请在调用替换 Public Key Token 实用程序和点到包含公钥标记的.snk 文件。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-114">The developer can configure the script to automatically substitute the new public key token, as follows: At the start of the script, invoke the Replace Public Key Token utility and point it to a .snk file that contains the public key token.</span></span> <span data-ttu-id="a9ecb-115">在脚本中，使用环境变量 %NEWTOKEN% 表示公钥标记。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-115">Within the script, use the environment variable %NEWTOKEN% to represent the public key token.</span></span> <span data-ttu-id="a9ecb-116">脚本运行时，实用程序从 .snk 文件中提取公钥标记的值，并将该值设置到环境变量 %NEWTOKEN% 中。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-116">When the script runs, the utility extracts the value of the public key token from the .snk file and sets it into an environment variable %NEWTOKEN%.</span></span> <span data-ttu-id="a9ecb-117">脚本运行时，将用指定的 .snk 文件中的公钥标记来替代 %NEWTOKEN% 的每个实例。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-117">When the script runs, each instance of %NEWTOKEN% will be with substituted with the public key token from the specified .snk file.</span></span> <span data-ttu-id="a9ecb-118">例如：</span><span class="sxs-lookup"><span data-stu-id="a9ecb-118">For example:</span></span>  
  
    ```  
    ReplacePKT.bat key.snk  
    ...  
    ...  
    gacutil /u Assembly, ... PublicKey=%NEWTOKEN% ...  
    ```  
  
## <a name="location-in-sdk"></a><span data-ttu-id="a9ecb-119">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="a9ecb-119">Location in SDK</span></span>  
 <span data-ttu-id="a9ecb-120">替换公钥标记实用程序位于：</span><span class="sxs-lookup"><span data-stu-id="a9ecb-120">The Replace Public Key Token utility is located in:</span></span>  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="a9ecb-121">SDK\Utilities\ReplacePublicKeyToken\\。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-121">SDK\Utilities\ReplacePublicKeyToken\\.</span></span>  
  
 <span data-ttu-id="a9ecb-122">替换公钥标记实用程序由三个文件组成：</span><span class="sxs-lookup"><span data-stu-id="a9ecb-122">The Replace Public Key Token utility comprises three files:</span></span>  
  
-   <span data-ttu-id="a9ecb-123">ReplacePKT.bat</span><span class="sxs-lookup"><span data-stu-id="a9ecb-123">ReplacePKT.bat</span></span>  
  
-   <span data-ttu-id="a9ecb-124">ReplacePKT.vbs</span><span class="sxs-lookup"><span data-stu-id="a9ecb-124">ReplacePKT.vbs</span></span>  
  
-   <span data-ttu-id="a9ecb-125">ReplacePKT.wsf</span><span class="sxs-lookup"><span data-stu-id="a9ecb-125">ReplacePKT.wsf</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="a9ecb-126">过程</span><span class="sxs-lookup"><span data-stu-id="a9ecb-126">Procedures</span></span>  
 <span data-ttu-id="a9ecb-127">使用以下过程，用从 .snk 文件中提取的公钥标记替换文件中公钥标记或占位符的所有实例，如方案 1 中所述。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-127">Use the following procedure to replace all instances of a public key token or a placeholder in a file with a public key token extracted from an .snk file, as described in Scenario 1.</span></span>  
  
#### <a name="to-replace-instances-of-a-public-key-token-or-a-placeholder-in-a-file"></a><span data-ttu-id="a9ecb-128">替换文件中公钥标记或占位符的实例</span><span class="sxs-lookup"><span data-stu-id="a9ecb-128">To replace instances of a public key token or a placeholder in a file</span></span>  
  
1.  <span data-ttu-id="a9ecb-129">确保本地计算机上具有以下所有文件：三个替换公钥标记实用程序文件（ReplacePKT.bat、ReplacePKT.vbs、ReplacePKT.wsf）、脚本文件和 .snk 文件。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-129">Make sure that the three Replace Public Key Token utility files (ReplacePKT.bat, ReplacePKT.vbs, ReplacePKT.wsf), the script file, and the .snk file are all available from the local computer.</span></span>  
  
2.  <span data-ttu-id="a9ecb-130">在命令窗口中，将目录更改到包含替换公钥标记实用程序文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-130">In a command window, change the directory to the folder containing the Replace Public Key utility files.</span></span>  
  
3.  <span data-ttu-id="a9ecb-131">从命令提示符处，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a9ecb-131">From a command prompt, run the following command:</span></span>  
  
4.  <span data-ttu-id="a9ecb-132">**ReplacePKT \<**  *.snk 文件*  **>  \<**  *旧的公钥令牌*  **>  \<**  *文件替换***>**</span><span class="sxs-lookup"><span data-stu-id="a9ecb-132">**ReplacePKT \<** *.snk file* **> \<** *old public key token* **> \<** *file to replace* **>**</span></span>  
  
    |<span data-ttu-id="a9ecb-133">选项</span><span class="sxs-lookup"><span data-stu-id="a9ecb-133">Option</span></span>|<span data-ttu-id="a9ecb-134">Description</span><span class="sxs-lookup"><span data-stu-id="a9ecb-134">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="a9ecb-135">**\<***.snk 文件***>**</span><span class="sxs-lookup"><span data-stu-id="a9ecb-135">**\<** *.snk file* **>**</span></span>|<span data-ttu-id="a9ecb-136">.snk 文件的完整路径，该文件中包含的公钥标记将替换现有的公钥标记或占位符 。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-136">Full path of the .snk file containing the public key token that you want substitute for the existing public key token or placeholder.</span></span>|  
    |<span data-ttu-id="a9ecb-137">**\<***旧的公钥令牌***>**</span><span class="sxs-lookup"><span data-stu-id="a9ecb-137">**\<** *old public key token* **>**</span></span>|<span data-ttu-id="a9ecb-138">要替换的公钥标记或占位符。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-138">Public key token or placeholder that you want to replace.</span></span>|  
    |<span data-ttu-id="a9ecb-139">**\<***文件替换***>**</span><span class="sxs-lookup"><span data-stu-id="a9ecb-139">**\<** *file to replace* **>**</span></span>|<span data-ttu-id="a9ecb-140">要替换的公钥标记或占位符所在文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-140">Full path of the file in which you want to replace the public key token or placeholder.</span></span>|  
  
     <span data-ttu-id="a9ecb-141">例如：</span><span class="sxs-lookup"><span data-stu-id="a9ecb-141">Example:</span></span>  
  
     <span data-ttu-id="a9ecb-142">**ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**</span><span class="sxs-lookup"><span data-stu-id="a9ecb-142">**ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**</span></span>  
  
 <span data-ttu-id="a9ecb-143">使用以下过程，自动设置脚本中使用从 .snk 文件中提取的公钥标记的环境变量，如方案 2 中所述。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-143">Use the following procedure to automatically set an environment variable in a script that uses a public key token derived from an .snk file, as described in Scenario 2.</span></span>  
  
#### <a name="to-set-an-environment-variable-that-uses-a-public-key-token"></a><span data-ttu-id="a9ecb-144">设置使用公钥标记的环境变量</span><span class="sxs-lookup"><span data-stu-id="a9ecb-144">To set an environment variable that uses a public key token</span></span>  
  
1.  <span data-ttu-id="a9ecb-145">在脚本文件的开始处，添加以下代码行：</span><span class="sxs-lookup"><span data-stu-id="a9ecb-145">At the beginning of your script file, add the following line of code:</span></span>  
  
    ```  
    ReplacePKT <filename>.snk  
    ```  
  
     <span data-ttu-id="a9ecb-146">其中\< *filename*> 是从中派生公钥标记的.snk 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-146">Where \<*filename*> is the name of the .snk file from which to derive the public key token.</span></span>  
  
    ```  
    Example: ReplacePKT.bat MyToken.snk  
    ```  
  
2.  <span data-ttu-id="a9ecb-147">在脚本文件中，使用`%NEWTOKEN%`来表示公钥标记。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-147">In your script file, use `%NEWTOKEN%` to represent the public key token.</span></span>  
  
     <span data-ttu-id="a9ecb-148">例如：</span><span class="sxs-lookup"><span data-stu-id="a9ecb-148">Example:</span></span>  
  
    ```  
    PublicKey=%NEWTOKEN%  
    ```  
  
3.  <span data-ttu-id="a9ecb-149">将脚本文件传送给用户时，请将组成替换公钥标记实用程序的三个文件（ReplacePKT.bat、ReplacePKT.vbs、ReplacePKT.wsf）包括在内。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-149">When you deliver your script file to your users, include the three files that comprise the Replace Public Key Token utility (ReplacePKT.bat, ReplacePKT.vbs, ReplacePKT.wsf).</span></span> <span data-ttu-id="a9ecb-150">确保脚本用户在运行脚本之前将这三个文件全部复制到文件系统中的同一文件夹。</span><span class="sxs-lookup"><span data-stu-id="a9ecb-150">Make sure that users of your script copy all of the files to the same folder on the file system before running your script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ecb-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9ecb-151">See Also</span></span>  
 [<span data-ttu-id="a9ecb-152">SDK 中的实用程序</span><span class="sxs-lookup"><span data-stu-id="a9ecb-152">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)