---
title: UninstallApp 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f45c9530-8138-40f1-b279-1428c5a7fbbc
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4fc9da4d645b710490447addc2d4fd8691f199d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292683"
---
# <a name="uninstallapp-command"></a><span data-ttu-id="0bce5-102">UninstallApp 命令</span><span class="sxs-lookup"><span data-stu-id="0bce5-102">UninstallApp Command</span></span>
<span data-ttu-id="0bce5-103">从本地计算机中卸载 BizTalk 应用程序，并从列表中的程序中添加或删除程序控制面板中移除应用程序。</span><span class="sxs-lookup"><span data-stu-id="0bce5-103">Uninstalls a BizTalk application from the local computer and also removes the application from the list of programs in Add or Remove Programs in Control Panel.</span></span> <span data-ttu-id="0bce5-104">此命令的效果删除应用程序通过添加或删除程序。</span><span class="sxs-lookup"><span data-stu-id="0bce5-104">This command has the same effect as removing an application by using Add or Remove Programs.</span></span> <span data-ttu-id="0bce5-105">如果为此应用程序安装了多个.msi 文件，将卸载的所有安装的.msi 文件的所有项。</span><span class="sxs-lookup"><span data-stu-id="0bce5-105">If multiple .msi files have been installed for this application, all of the items installed by all of the .msi files are uninstalled.</span></span>  
  
 <span data-ttu-id="0bce5-106">添加或删除程序中所示，此命令指定的应用程序名称必须与应用程序的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="0bce5-106">The application name that you specify for this command must match the name of the application as displayed in Add or Remove Programs.</span></span> <span data-ttu-id="0bce5-107">如果您不确定的应用程序名称，则可以使用**ListPackage**命令来获取它，如中所述[ListPackage 命令](../core/listpackage-command.md)。</span><span class="sxs-lookup"><span data-stu-id="0bce5-107">If you are unsure of the application name, you can use the **ListPackage** command to obtain it, as described in [ListPackage Command](../core/listpackage-command.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0bce5-108">尽管可以通过双击.msi 文件卸载的应用程序，但不支持执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0bce5-108">Although it is possible to uninstall an application by double-clicking the .msi file, doing this is not supported.</span></span> <span data-ttu-id="0bce5-109">这是因为可以为同一应用程序，安装多个.msi 文件并使用此方法将不会卸载所有应用程序与关联的项。</span><span class="sxs-lookup"><span data-stu-id="0bce5-109">This is because multiple .msi files can be installed for the same application, and using this method will not uninstall all of the items associated with the application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="0bce5-110">用法</span><span class="sxs-lookup"><span data-stu-id="0bce5-110">Usage</span></span>  
 <span data-ttu-id="0bce5-111">**BTSTask UninstallApp /ApplicationName:** *值*</span><span class="sxs-lookup"><span data-stu-id="0bce5-111">**BTSTask UninstallApp /ApplicationName:** *value*</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="0bce5-112">Parameters</span><span class="sxs-lookup"><span data-stu-id="0bce5-112">Parameters</span></span>  
  
|<span data-ttu-id="0bce5-113">参数</span><span class="sxs-lookup"><span data-stu-id="0bce5-113">Parameter</span></span>|<span data-ttu-id="0bce5-114">Required</span><span class="sxs-lookup"><span data-stu-id="0bce5-114">Required</span></span>|<span data-ttu-id="0bce5-115">Description</span><span class="sxs-lookup"><span data-stu-id="0bce5-115">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="0bce5-116">**/ ApplicationName** (或 **/A**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="0bce5-116">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="0bce5-117">是</span><span class="sxs-lookup"><span data-stu-id="0bce5-117">Yes</span></span>|<span data-ttu-id="0bce5-118">若要卸载的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="0bce5-118">Name of the BizTalk application to uninstall.</span></span> <span data-ttu-id="0bce5-119">如果名称包含空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="0bce5-119">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="0bce5-120">示例</span><span class="sxs-lookup"><span data-stu-id="0bce5-120">Sample</span></span>  
 <span data-ttu-id="0bce5-121">**BTSTask UninstallApp /ApplicationName:MyApplication**</span><span class="sxs-lookup"><span data-stu-id="0bce5-121">**BTSTask UninstallApp /ApplicationName:MyApplication**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bce5-122">备注</span><span class="sxs-lookup"><span data-stu-id="0bce5-122">Remarks</span></span>  
 <span data-ttu-id="0bce5-123">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0bce5-123">Parameters are not case-sensitive.</span></span> <span data-ttu-id="0bce5-124">不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。</span><span class="sxs-lookup"><span data-stu-id="0bce5-124">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bce5-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bce5-125">See Also</span></span>  
 <span data-ttu-id="0bce5-126">[BTSTask 命令行参考](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0bce5-126">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="0bce5-127">如何卸载 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="0bce5-127">How to Uninstall a BizTalk Application</span></span>](../core/how-to-uninstall-a-biztalk-application.md)