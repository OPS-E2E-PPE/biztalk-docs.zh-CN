---
title: "UninstallApp 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f45c9530-8138-40f1-b279-1428c5a7fbbc
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea94335882ffbcf01b69c450ef4a5eb80ef4fa3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="uninstallapp-command"></a><span data-ttu-id="3f61d-102">UninstallApp 命令</span><span class="sxs-lookup"><span data-stu-id="3f61d-102">UninstallApp Command</span></span>
<span data-ttu-id="3f61d-103">该命令从本地计算机中卸载 BizTalk 应用程序，并且将从“控制面板”的“添加或删除程序”中的程序列表中删除该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3f61d-103">Uninstalls a BizTalk application from the local computer and also removes the application from the list of programs in Add or Remove Programs in Control Panel.</span></span> <span data-ttu-id="3f61d-104">此命令与使用“添加或删除程序”删除应用程序的效果相同。</span><span class="sxs-lookup"><span data-stu-id="3f61d-104">This command has the same effect as removing an application by using Add or Remove Programs.</span></span> <span data-ttu-id="3f61d-105">如果为要删除的应用程序安装了多个 .msi 文件，则所有这些 .msi 文件安装的全部项都将被卸载。</span><span class="sxs-lookup"><span data-stu-id="3f61d-105">If multiple .msi files have been installed for this application, all of the items installed by all of the .msi files are uninstalled.</span></span>  
  
 <span data-ttu-id="3f61d-106">为此命令指定的应用程序名称必须与显示在“添加或删除程序”中的应用程序名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="3f61d-106">The application name that you specify for this command must match the name of the application as displayed in Add or Remove Programs.</span></span> <span data-ttu-id="3f61d-107">如果您不确定的应用程序名称，则可以使用**ListPackage**命令以获取它中, 所述[ListPackage 命令](../core/listpackage-command.md)。</span><span class="sxs-lookup"><span data-stu-id="3f61d-107">If you are unsure of the application name, you can use the **ListPackage** command to obtain it, as described in [ListPackage Command](../core/listpackage-command.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3f61d-108">虽然通过双击 .msi 文件能够卸载应用程序，但建议不要这样做。</span><span class="sxs-lookup"><span data-stu-id="3f61d-108">Although it is possible to uninstall an application by double-clicking the .msi file, doing this is not supported.</span></span> <span data-ttu-id="3f61d-109">因为可以为同一个应用程序安装多个 .msi 文件，如果采用这种方法卸载应用程序，将不能卸载与该应用程序相关联的所有项。</span><span class="sxs-lookup"><span data-stu-id="3f61d-109">This is because multiple .msi files can be installed for the same application, and using this method will not uninstall all of the items associated with the application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="3f61d-110">用法</span><span class="sxs-lookup"><span data-stu-id="3f61d-110">Usage</span></span>  
 <span data-ttu-id="3f61d-111">**BTSTask UninstallApp /ApplicationName:** *值*</span><span class="sxs-lookup"><span data-stu-id="3f61d-111">**BTSTask UninstallApp /ApplicationName:** *value*</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="3f61d-112">Parameters</span><span class="sxs-lookup"><span data-stu-id="3f61d-112">Parameters</span></span>  
  
|<span data-ttu-id="3f61d-113">参数</span><span class="sxs-lookup"><span data-stu-id="3f61d-113">Parameter</span></span>|<span data-ttu-id="3f61d-114">必需</span><span class="sxs-lookup"><span data-stu-id="3f61d-114">Required</span></span>|<span data-ttu-id="3f61d-115">Description</span><span class="sxs-lookup"><span data-stu-id="3f61d-115">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="3f61d-116">**/ ApplicationName** (或**/A**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="3f61d-116">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="3f61d-117">是</span><span class="sxs-lookup"><span data-stu-id="3f61d-117">Yes</span></span>|<span data-ttu-id="3f61d-118">要卸载的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="3f61d-118">Name of the BizTalk application to uninstall.</span></span> <span data-ttu-id="3f61d-119">如果名称包含空格，必须将它括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="3f61d-119">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="3f61d-120">示例</span><span class="sxs-lookup"><span data-stu-id="3f61d-120">Sample</span></span>  
 <span data-ttu-id="3f61d-121">**BTSTask UninstallApp /ApplicationName:MyApplication**</span><span class="sxs-lookup"><span data-stu-id="3f61d-121">**BTSTask UninstallApp /ApplicationName:MyApplication**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f61d-122">注释</span><span class="sxs-lookup"><span data-stu-id="3f61d-122">Remarks</span></span>  
 <span data-ttu-id="3f61d-123">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="3f61d-123">Parameters are not case-sensitive.</span></span> <span data-ttu-id="3f61d-124">指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。</span><span class="sxs-lookup"><span data-stu-id="3f61d-124">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f61d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f61d-125">See Also</span></span>  
 <span data-ttu-id="3f61d-126">[BTSTask 命令行参考](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3f61d-126">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="3f61d-127">如何卸载 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="3f61d-127">How to Uninstall a BizTalk Application</span></span>](../core/how-to-uninstall-a-biztalk-application.md)