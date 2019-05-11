---
title: 导入基于 XSD 的 PIP |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, importing
- XSD-based PIPs
- PIPs, XSD-based PIPs
ms.assetid: d12441d4-79bf-4c24-9360-4b78c1da0d34
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8d1a0d6b4fe835a38dc5eaf19a328b14e0d288f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283674"
---
# <a name="importing-an-xsd-based-pip"></a><span data-ttu-id="f13af-102">导入基于 XSD 的 PIP</span><span class="sxs-lookup"><span data-stu-id="f13af-102">Importing an XSD-based PIP</span></span>
<span data-ttu-id="f13af-103">尽管大部分 RosettaNet.org 所提供的 PIP 是基于 DTD 的、 较新的 PIP 是基于 XSD 的。</span><span class="sxs-lookup"><span data-stu-id="f13af-103">While the majority of PIPS provided by RosettaNet.org are DTD-based, newer PIPS are XSD-based.</span></span> <span data-ttu-id="f13af-104">以下过程描述如何导入基于 XSD 的 PIP。</span><span class="sxs-lookup"><span data-stu-id="f13af-104">The following procedure describes how to import XSD-based PIPS.</span></span>  
  
### <a name="to-import-an-xsd-based-pip"></a><span data-ttu-id="f13af-105">若要导入基于 XSD 的 PIP</span><span class="sxs-lookup"><span data-stu-id="f13af-105">To import an XSD-based PIP</span></span>  
  
1.  <span data-ttu-id="f13af-106">从 rosettanet.org 下载得到处下载基于 XSD 的 PIP 的.zip 文件[ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=33859)或在 cidx.org [ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=62361)。</span><span class="sxs-lookup"><span data-stu-id="f13af-106">Download the XSD-based PIP .zip file from RosettaNet.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859) or from CIDX.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span></span> <span data-ttu-id="f13af-107">从.zip 文件中提取文件。</span><span class="sxs-lookup"><span data-stu-id="f13af-107">Extract the files from the .zip file.</span></span> <span data-ttu-id="f13af-108">所需的文件将 XML 文件夹的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f13af-108">The files that you need will be in the subfolders of the XML folder.</span></span>  
  
2.  <span data-ttu-id="f13af-109">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="f13af-109">Open Visual Studio.</span></span> <span data-ttu-id="f13af-110">创建新的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="f13af-110">Create a new BizTalk project.</span></span>  
  
3.  <span data-ttu-id="f13af-111">打开 Windows 资源管理器，然后转到在步骤 1 中提取的 XML 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f13af-111">Open Windows Explorer, and move to the XML folder extracted in step 1.</span></span> <span data-ttu-id="f13af-112">选择 XML 文件夹下的第一个文件夹，将其拖到解决方案资源管理器在 Visual Studio 中，并放入项目。</span><span class="sxs-lookup"><span data-stu-id="f13af-112">Select the first folder under the XML folder, drag it to Solutions Explorer in Visual Studio, and drop it into your project.</span></span> <span data-ttu-id="f13af-113">重复的每个子文件夹中的 XML 文件夹中，在你的项目中创建的相同文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="f13af-113">Repeat for each of the subfolders in the XML folder, creating the same folder structure in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f13af-114">对于 PIP7c7 PIP 这些文件夹将包括域、 交换、 系统和通用文件夹。</span><span class="sxs-lookup"><span data-stu-id="f13af-114">For a PIP7c7 PIP these folders would include the Domain, Interchange, System, and Universal folders.</span></span> <span data-ttu-id="f13af-115">对于此 PIP，你的项目应包含域、 交换、 系统和通用文件夹和其内容。</span><span class="sxs-lookup"><span data-stu-id="f13af-115">For this PIP, your project should contain Domain, Interchange, System, and Universal folders and their contents.</span></span>  
  
4.  <span data-ttu-id="f13af-116">如果系统文件夹中没有一个.xsd 文件，在解决方案资源管理器中选择它并更改，以便它不包含字符串的属性页中列出的命名空间"。系统"。</span><span class="sxs-lookup"><span data-stu-id="f13af-116">If there is an .xsd file in the System folder, select it in Solution Explorer and change the namespace listed in the property page so that it does not contain the string ".System".</span></span> <span data-ttu-id="f13af-117">例如，对于 PIP7c7 PIP，可以更改命名空间为"PIP7c7._System"。</span><span class="sxs-lookup"><span data-stu-id="f13af-117">For example, for PIP7c7 PIP, you could change the namespace to be "PIP7c7._System".</span></span> <span data-ttu-id="f13af-118">每个.xsd 文件重复系统文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f13af-118">Repeat for each .xsd file in the System folder.</span></span> <span data-ttu-id="f13af-119">如果不更改命名空间，你将收到以下或类似的错误消息：</span><span class="sxs-lookup"><span data-stu-id="f13af-119">If you do not change the namespace, you will receive the following or a similar error:</span></span>  
  
    ```  
    The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'PIP7C7.System'.  
    ```  
  
5.  <span data-ttu-id="f13af-120">检查所有.xsd 文件，以确保\<架构\>类型名与根节点的类型名不相同。</span><span class="sxs-lookup"><span data-stu-id="f13af-120">Review all .xsd files to ensure that the \<schema\> TypeName and root node TypeName are not identical.</span></span> <span data-ttu-id="f13af-121">例如，对于 PIP7C7 PIP 的 Universal 文件夹中 PartnerIdentification.xsd 具有 TypeName partneridentification 两个\<架构\>（当 PartnerIdentification.xsd 在解决方案资源管理器中选择） 以及PartnerIdentification 根结点。</span><span class="sxs-lookup"><span data-stu-id="f13af-121">For example, for a PIP7C7 PIP the PartnerIdentification.xsd in the Universal folder has the TypeName of 'PartnerIdentification' for both the \<schema\> (when PartnerIdentification.xsd is selected in Solution Explorer) and also the PartnerIdentification root node.</span></span> <span data-ttu-id="f13af-122">若要更正此问题，在解决方案资源管理器中选择 PartnerIdentification.xsd，然后在属性页中更改的 TypeName 属性，以便它不包含类型名与 PartnerIdentification 根结点。</span><span class="sxs-lookup"><span data-stu-id="f13af-122">To correct this, select PartnerIdentification.xsd in Solution Explorer, and then in the property page change the TypeName property so that it does not contain the same TypeName as the PartnerIdentification root node.</span></span> <span data-ttu-id="f13af-123">例如，更改类型名称为"_PartnerIdentification"。</span><span class="sxs-lookup"><span data-stu-id="f13af-123">For example, change the TypeName to be "_PartnerIdentification".</span></span> <span data-ttu-id="f13af-124">如果不执行此步骤，将收到以下错误，当你尝试生成项目时：</span><span class="sxs-lookup"><span data-stu-id="f13af-124">If you do not take this step, you will receive the following error when you try to build the project:</span></span>  
  
    ```  
    Node "<Schema>" - This schema file has a TypeName that collides with the RootNode TypeName of one of its root Nodes. Make sure that they are different.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f13af-125">错误列表中的文件列将指示哪些文件会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="f13af-125">The File column in the error list will indicate which files have this problem.</span></span>  
  
6.  <span data-ttu-id="f13af-126">生成，然后部署该项目。</span><span class="sxs-lookup"><span data-stu-id="f13af-126">Build and then deploy the project.</span></span>