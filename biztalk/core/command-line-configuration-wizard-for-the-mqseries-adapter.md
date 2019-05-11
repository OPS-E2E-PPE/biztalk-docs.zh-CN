---
title: MQSeries 适配器的命令行配置向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], Command-Line Configuration Wizard
- Command-Line Configuration Wizard
- MQSeries adapters, Command-Line Configuration Wizard
ms.assetid: cab905d1-fe19-4d6a-be1b-f561e133e1d2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 174e40f413be4ae3fab89965b842dee8fb8ba513
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357718"
---
# <a name="command-line-configuration-wizard-for-the-mqseries-adapter"></a><span data-ttu-id="2e88b-102">MQSeries 适配器的命令行配置向导</span><span class="sxs-lookup"><span data-stu-id="2e88b-102">Command-Line Configuration Wizard for the MQSeries Adapter</span></span>
<span data-ttu-id="2e88b-103">该向导具有四个选项用于安装、 卸载和日志记录操作。</span><span class="sxs-lookup"><span data-stu-id="2e88b-103">The wizard has four options for installing, uninstalling, and logging actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e88b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e88b-104">Syntax</span></span>  
 <span data-ttu-id="2e88b-105">**mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**</span><span class="sxs-lookup"><span data-stu-id="2e88b-105">**mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**</span></span>  
  
|<span data-ttu-id="2e88b-106">Option</span><span class="sxs-lookup"><span data-stu-id="2e88b-106">Option</span></span>|<span data-ttu-id="2e88b-107">Description</span><span class="sxs-lookup"><span data-stu-id="2e88b-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2e88b-108">**/u**</span><span class="sxs-lookup"><span data-stu-id="2e88b-108">**/u**</span></span>|<span data-ttu-id="2e88b-109">卸载 MQSAgent。</span><span class="sxs-lookup"><span data-stu-id="2e88b-109">Uninstalls the MQSAgent.</span></span>|  
|<span data-ttu-id="2e88b-110">**/i** *config.xml*</span><span class="sxs-lookup"><span data-stu-id="2e88b-110">**/i** *config.xml*</span></span>|<span data-ttu-id="2e88b-111">安装在文件中使用的信息 MQSAgent *config.xml*。</span><span class="sxs-lookup"><span data-stu-id="2e88b-111">Installs the MQSAgent using the information in the file *config.xml*.</span></span>|  
|<span data-ttu-id="2e88b-112">**/l** *logfile*</span><span class="sxs-lookup"><span data-stu-id="2e88b-112">**/l** *logfile*</span></span>|<span data-ttu-id="2e88b-113">记录到文件的操作*日志文件*。</span><span class="sxs-lookup"><span data-stu-id="2e88b-113">Logs actions to the file *logfile*.</span></span>|  
|<span data-ttu-id="2e88b-114">**/?**</span><span class="sxs-lookup"><span data-stu-id="2e88b-114">**/?**</span></span>|<span data-ttu-id="2e88b-115">显示说明命令行选项的对话框。</span><span class="sxs-lookup"><span data-stu-id="2e88b-115">Displays a dialog box describing the command-line options.</span></span>|  
  
 <span data-ttu-id="2e88b-116">包含配置信息的 XML 文件的内容可能不同，具体取决于正在使用的 Windows 版本。</span><span class="sxs-lookup"><span data-stu-id="2e88b-116">The contents of the XML file that contains the configuration information may vary, depending on the version of Windows you are using.</span></span> <span data-ttu-id="2e88b-117">有关配置文件格式的详细信息，请参阅[MQSeries 适配器的 XML 配置文件](../core/xml-configuration-file-for-the-mqseries-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="2e88b-117">For more information about the configuration file format, see [XML Configuration File for the MQSeries Adapter](../core/xml-configuration-file-for-the-mqseries-adapter.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2e88b-118">运行配置向导时，适配器不会正常工作。</span><span class="sxs-lookup"><span data-stu-id="2e88b-118">The adapter does not work while the configuration wizard is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e88b-119">您不能使用命令行配置向导重新配置 MQSAgent。</span><span class="sxs-lookup"><span data-stu-id="2e88b-119">You cannot reconfigure MQSAgent with the command-line configuration wizard.</span></span> <span data-ttu-id="2e88b-120">必须先运行向导以卸载代理 (**/u**)，然后运行它来配置 (**/i**)。</span><span class="sxs-lookup"><span data-stu-id="2e88b-120">You must first run the wizard to uninstall the agent (**/u**), and then run it to configure (**/i**).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e88b-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e88b-121">See Also</span></span>  
 [<span data-ttu-id="2e88b-122">MQSeries 适配器的无提示配置</span><span class="sxs-lookup"><span data-stu-id="2e88b-122">Silent Configuration of the MQSeries Adapter</span></span>](../core/silent-configuration-of-the-mqseries-adapter.md)