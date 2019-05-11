---
title: 使用预处理和后处理脚本自定义应用程序部署 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- customizing, applications
- applications, customizing
- scripts, applications
- scripts, customizing
ms.assetid: 47627394-d594-491b-9098-38c5d028a378
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23734f43a479e4e526535b61f0e9b957752e03d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396572"
---
# <a name="using-pre--and-post-processing-scripts-to-customize-application-deployment"></a><span data-ttu-id="b257b-102">使用预处理和后处理脚本自定义应用程序部署</span><span class="sxs-lookup"><span data-stu-id="b257b-102">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>
<span data-ttu-id="b257b-103">在本部分中的主题介绍如何创建预处理或后处理脚本来执行的操作导入应用程序时，安装或卸载。</span><span class="sxs-lookup"><span data-stu-id="b257b-103">The topics in this section describe how to create pre- or post-processing scripts to perform actions when an application is imported, installed, or uninstalled.</span></span> <span data-ttu-id="b257b-104">应用程序导入或安装开始前以及卸载完成后，预处理脚本执行的操作或组的操作。</span><span class="sxs-lookup"><span data-stu-id="b257b-104">Pre-processing scripts perform an action or set of actions before application import or installation starts, and after uninstallation completes.</span></span> <span data-ttu-id="b257b-105">应用程序导入或安装完成后，或在卸载开始前，后续处理脚本执行一个操作或一组操作。</span><span class="sxs-lookup"><span data-stu-id="b257b-105">Post-processing scripts perform an action or set of actions after application import or installation completes, or before uninstallation starts.</span></span>  
  
 <span data-ttu-id="b257b-106">例如，可能想要包括在安装之前安装过程中覆盖备份资源文件前将运行的预处理脚本。</span><span class="sxs-lookup"><span data-stu-id="b257b-106">You might, for example, want to include a pre-processing script that will run before installation to back up resource files before they are overwritten during installation.</span></span> <span data-ttu-id="b257b-107">或者，可能想要运行一个后处理脚本来安装应用程序后，将证书添加到证书存储区。</span><span class="sxs-lookup"><span data-stu-id="b257b-107">Or you might want to run a post-processing script to add a certificate to the certificate store after an application is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b257b-108">BizTalk Server 包含示例预处理和后处理脚本。</span><span class="sxs-lookup"><span data-stu-id="b257b-108">BizTalk Server includes sample pre- and post-processing scripts.</span></span> <span data-ttu-id="b257b-109">有关使用示例脚本的信息，请参阅[模板 （应用程序部署示例）](../core/template-application-deployment-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="b257b-109">For information about using the sample scripts, see [Template (Application Deployment Sample)](../core/template-application-deployment-sample.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b257b-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="b257b-110">In This Section</span></span>  
  
-   [<span data-ttu-id="b257b-111">创建预处理脚本或后期处理脚本</span><span class="sxs-lookup"><span data-stu-id="b257b-111">Creating a Pre- or Post-processing Script</span></span>](../core/creating-a-pre-or-post-processing-script.md)  
  
-   [<span data-ttu-id="b257b-112">环境变量如何指示部署状态</span><span class="sxs-lookup"><span data-stu-id="b257b-112">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)  
  
-   [<span data-ttu-id="b257b-113">部署过程中的文件项目状态</span><span class="sxs-lookup"><span data-stu-id="b257b-113">Status of File Artifacts During Deployment</span></span>](../core/status-of-file-artifacts-during-deployment.md)  
  
-   [<span data-ttu-id="b257b-114">预处理脚本和后期处理脚本环境变量</span><span class="sxs-lookup"><span data-stu-id="b257b-114">Pre- and Post-processing Script Environment Variables</span></span>](../core/pre-and-post-processing-script-environment-variables.md)