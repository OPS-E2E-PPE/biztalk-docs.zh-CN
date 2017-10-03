---
title: "命令行配置向导为 MQSeries 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], Command-Line Configuration Wizard
- Command-Line Configuration Wizard
- MQSeries adapters, Command-Line Configuration Wizard
ms.assetid: cab905d1-fe19-4d6a-be1b-f561e133e1d2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee73b890fca43a3651f22092486e5898862b0b72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="command-line-configuration-wizard-for-the-mqseries-adapter"></a><span data-ttu-id="58a9d-102">MQSeries 适配器的命令行配置向导</span><span class="sxs-lookup"><span data-stu-id="58a9d-102">Command-Line Configuration Wizard for the MQSeries Adapter</span></span>
<span data-ttu-id="58a9d-103">该向导具有四个用于安装、卸载和记录操作的选项。</span><span class="sxs-lookup"><span data-stu-id="58a9d-103">The wizard has four options for installing, uninstalling, and logging actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58a9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="58a9d-104">Syntax</span></span>  
 <span data-ttu-id="58a9d-105">**mqsconfigwiz [/u] [/i config.xml] [/l 日志文件] [/？]**</span><span class="sxs-lookup"><span data-stu-id="58a9d-105">**mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**</span></span>  
  
|<span data-ttu-id="58a9d-106">选项</span><span class="sxs-lookup"><span data-stu-id="58a9d-106">Option</span></span>|<span data-ttu-id="58a9d-107">Description</span><span class="sxs-lookup"><span data-stu-id="58a9d-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="58a9d-108">**/u**</span><span class="sxs-lookup"><span data-stu-id="58a9d-108">**/u**</span></span>|<span data-ttu-id="58a9d-109">卸载 MQSAgent。</span><span class="sxs-lookup"><span data-stu-id="58a9d-109">Uninstalls the MQSAgent.</span></span>|  
|<span data-ttu-id="58a9d-110">**/i** *config.xml*</span><span class="sxs-lookup"><span data-stu-id="58a9d-110">**/i** *config.xml*</span></span>|<span data-ttu-id="58a9d-111">安装在文件中使用信息 MQSAgent *config.xml*。</span><span class="sxs-lookup"><span data-stu-id="58a9d-111">Installs the MQSAgent using the information in the file *config.xml*.</span></span>|  
|<span data-ttu-id="58a9d-112">**/l** *日志文件*</span><span class="sxs-lookup"><span data-stu-id="58a9d-112">**/l** *logfile*</span></span>|<span data-ttu-id="58a9d-113">会将操作记录到文件*日志文件*。</span><span class="sxs-lookup"><span data-stu-id="58a9d-113">Logs actions to the file *logfile*.</span></span>|  
|<span data-ttu-id="58a9d-114">**/?**</span><span class="sxs-lookup"><span data-stu-id="58a9d-114">**/?**</span></span>|<span data-ttu-id="58a9d-115">显示了对命令行选项进行说明的对话框。</span><span class="sxs-lookup"><span data-stu-id="58a9d-115">Displays a dialog box describing the command-line options.</span></span>|  
  
 <span data-ttu-id="58a9d-116">包含配置信息的 XML 文件的内容根据使用的 Windows 版本而可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="58a9d-116">The contents of the XML file that contains the configuration information may vary, depending on the version of Windows you are using.</span></span> <span data-ttu-id="58a9d-117">有关配置文件格式的详细信息，请参阅[MQSeries 适配器的 XML 配置文件](../core/xml-configuration-file-for-the-mqseries-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="58a9d-117">For more information about the configuration file format, see [XML Configuration File for the MQSeries Adapter](../core/xml-configuration-file-for-the-mqseries-adapter.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58a9d-118">在运行该配置向导时，适配器将不能工作。</span><span class="sxs-lookup"><span data-stu-id="58a9d-118">The adapter does not work while the configuration wizard is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58a9d-119">您不能用命令行配置向导重新配置 MQSAgent。</span><span class="sxs-lookup"><span data-stu-id="58a9d-119">You cannot reconfigure MQSAgent with the command-line configuration wizard.</span></span> <span data-ttu-id="58a9d-120">你必须先运行卸载代理向导 (**/u**)，然后运行该配置 (**/i**)。</span><span class="sxs-lookup"><span data-stu-id="58a9d-120">You must first run the wizard to uninstall the agent (**/u**), and then run it to configure (**/i**).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a9d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58a9d-121">See Also</span></span>  
 [<span data-ttu-id="58a9d-122">无提示 MQSeries 适配器配置</span><span class="sxs-lookup"><span data-stu-id="58a9d-122">Silent Configuration of the MQSeries Adapter</span></span>](../core/silent-configuration-of-the-mqseries-adapter.md)