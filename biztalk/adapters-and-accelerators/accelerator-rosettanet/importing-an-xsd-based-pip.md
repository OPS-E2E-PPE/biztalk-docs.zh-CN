---
title: "导入基于 XSD 的 PIP |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PIPs, importing
- XSD-based PIPs
- PIPs, XSD-based PIPs
ms.assetid: d12441d4-79bf-4c24-9360-4b78c1da0d34
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf0ced3dbb9404cd1c4b9c81e566f47b09c7d0b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-an-xsd-based-pip"></a><span data-ttu-id="052dd-102">导入基于 XSD 的 PIP</span><span class="sxs-lookup"><span data-stu-id="052dd-102">Importing an XSD-based PIP</span></span>
<span data-ttu-id="052dd-103">虽然 RosettaNet.org 所提供的大部分 PIP 是基于 DTD 的，但较新的 PIP 是基于 XSD 的。</span><span class="sxs-lookup"><span data-stu-id="052dd-103">While the majority of PIPS provided by RosettaNet.org are DTD-based, newer PIPS are XSD-based.</span></span> <span data-ttu-id="052dd-104">以下过程描述如何导入基于 XSD 的 PIP。</span><span class="sxs-lookup"><span data-stu-id="052dd-104">The following procedure describes how to import XSD-based PIPS.</span></span>  
  
### <a name="to-import-an-xsd-based-pip"></a><span data-ttu-id="052dd-105">导入基于 XSD 的 PIP</span><span class="sxs-lookup"><span data-stu-id="052dd-105">To import an XSD-based PIP</span></span>  
  
1.  <span data-ttu-id="052dd-106">在 RosettaNet.org 从下载基于 XSD 的 PIP.zip 文件[http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)或从在 CIDX.org [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361)。</span><span class="sxs-lookup"><span data-stu-id="052dd-106">Download the XSD-based PIP .zip file from RosettaNet.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859) or from CIDX.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span></span> <span data-ttu-id="052dd-107">从该 .zip 文件中提取文件。</span><span class="sxs-lookup"><span data-stu-id="052dd-107">Extract the files from the .zip file.</span></span> <span data-ttu-id="052dd-108">你所需要的文件位于 XML 文件夹的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="052dd-108">The files that you need will be in the subfolders of the XML folder.</span></span>  
  
2.  <span data-ttu-id="052dd-109">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="052dd-109">Open Visual Studio.</span></span> <span data-ttu-id="052dd-110">创建新 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="052dd-110">Create a new BizTalk project.</span></span>  
  
3.  <span data-ttu-id="052dd-111">打开 Windows 资源管理器，转到在步骤 1 中提取的 XML 文件夹。</span><span class="sxs-lookup"><span data-stu-id="052dd-111">Open Windows Explorer, and move to the XML folder extracted in step 1.</span></span> <span data-ttu-id="052dd-112">选择 XML 文件夹下的第一个文件夹，将其拖到 Visual Studio 的解决方案资源管理器中，然后将其放到您的项目中。</span><span class="sxs-lookup"><span data-stu-id="052dd-112">Select the first folder under the XML folder, drag it to Solutions Explorer in Visual Studio, and drop it into your project.</span></span> <span data-ttu-id="052dd-113">对 XML 文件夹中的每个子文件夹重复上述步骤，在你的项目中创建相同的文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="052dd-113">Repeat for each of the subfolders in the XML folder, creating the same folder structure in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="052dd-114">对于 PIP7c7 PIP，这些文件夹应包含 Domain、Interchange、System 和 Universal 文件夹。</span><span class="sxs-lookup"><span data-stu-id="052dd-114">For a PIP7c7 PIP these folders would include the Domain, Interchange, System, and Universal folders.</span></span> <span data-ttu-id="052dd-115">对于此 PIP，你的项目应包含 Domain、Interchange、System 和 Universal 文件夹及这些文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="052dd-115">For this PIP, your project should contain Domain, Interchange, System, and Universal folders and their contents.</span></span>  
  
4.  <span data-ttu-id="052dd-116">如果 System 文件夹中有 .xsd 文件，则请在解决方案资源管理器中选择该文件，然后更改属性页中列出的命名空间，以使其不包含字符串“.System”。</span><span class="sxs-lookup"><span data-stu-id="052dd-116">If there is an .xsd file in the System folder, select it in Solution Explorer and change the namespace listed in the property page so that it does not contain the string ".System".</span></span> <span data-ttu-id="052dd-117">例如对于 PIP7c7 PIP，可以将命名空间更改为“PIP7c7._System”。</span><span class="sxs-lookup"><span data-stu-id="052dd-117">For example, for PIP7c7 PIP, you could change the namespace to be "PIP7c7._System".</span></span> <span data-ttu-id="052dd-118">对 System 文件夹中的每个 .xsd 文件重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="052dd-118">Repeat for each .xsd file in the System folder.</span></span> <span data-ttu-id="052dd-119">如果不更改命名空间，你将收到以下错误或类似的错误：</span><span class="sxs-lookup"><span data-stu-id="052dd-119">If you do not change the namespace, you will receive the following or a similar error:</span></span>  
  
    ```  
    The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'PIP7C7.System'.  
    ```  
  
5.  <span data-ttu-id="052dd-120">查看所有.xsd 文件，以确保\<架构 > e，根节点类型名称不相同。</span><span class="sxs-lookup"><span data-stu-id="052dd-120">Review all .xsd files to ensure that the \<schema> TypeName and root node TypeName are not identical.</span></span> <span data-ttu-id="052dd-121">例如，对于 PIP7C7 PIP PartnerIdentification.xsd 通用文件夹中的具有 PartnerIdentification 的类型名称为\<架构 > （当 PartnerIdentification.xsd 在解决方案资源管理器中选择） 以及PartnerIdentification 根节点。</span><span class="sxs-lookup"><span data-stu-id="052dd-121">For example, for a PIP7C7 PIP the PartnerIdentification.xsd in the Universal folder has the TypeName of 'PartnerIdentification' for both the \<schema> (when PartnerIdentification.xsd is selected in Solution Explorer) and also the PartnerIdentification root node.</span></span> <span data-ttu-id="052dd-122">若要更正此错误，请在解决方案资源管理器中选择 PartnerIdentification.xsd，然后在属性页中更改类型名属性，以使其类型名与 PartnerIdentification 根结点不同。</span><span class="sxs-lookup"><span data-stu-id="052dd-122">To correct this, select PartnerIdentification.xsd in Solution Explorer, and then in the property page change the TypeName property so that it does not contain the same TypeName as the PartnerIdentification root node.</span></span> <span data-ttu-id="052dd-123">例如，可将类型名更改为“_PartnerIdentification”。</span><span class="sxs-lookup"><span data-stu-id="052dd-123">For example, change the TypeName to be "_PartnerIdentification".</span></span> <span data-ttu-id="052dd-124">如果不执行此步骤，则在尝试生成项目时将会收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="052dd-124">If you do not take this step, you will receive the following error when you try to build the project:</span></span>  
  
    ```  
    Node "<Schema>" - This schema file has a TypeName that collides with the RootNode TypeName of one of its root Nodes. Make sure that they are different.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="052dd-125">错误列表中的“文件”列将指出那些文件包含此问题。</span><span class="sxs-lookup"><span data-stu-id="052dd-125">The File column in the error list will indicate which files have this problem.</span></span>  
  
6.  <span data-ttu-id="052dd-126">生成然后部署项目。</span><span class="sxs-lookup"><span data-stu-id="052dd-126">Build and then deploy the project.</span></span>