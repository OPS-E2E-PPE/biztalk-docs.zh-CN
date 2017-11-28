---
title: "添加 Web 引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- orchestrations, BPEL
- Web services, ports
- orchestrations, exporting
- Web services, projects
- Web services, references
- projects, Web services
ms.assetid: 7e40f215-f11a-4151-bcc6-e107bf36b6f6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bcdeb4966da4a4b54fea826590f867e4125d2ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-web-references"></a><span data-ttu-id="0a869-102">添加 Web 引用</span><span class="sxs-lookup"><span data-stu-id="0a869-102">Adding Web References</span></span>
<span data-ttu-id="0a869-103">在添加 Web 端口之前，需要向 BizTalk 项目添加 Web 引用。</span><span class="sxs-lookup"><span data-stu-id="0a869-103">Before you can add a Web port, you need to add a Web reference to your BizTalk project.</span></span> <span data-ttu-id="0a869-104">Web 引用是对可用于你的项目的 Web Services 的说明。</span><span class="sxs-lookup"><span data-stu-id="0a869-104">A Web reference is a description of a Web service that is available to your project.</span></span> <span data-ttu-id="0a869-105">BizTalk 项目添加到你的项目的 Web 引用时，创建业务流程 Web 端口类型，Web 消息类型，（映射文件） Reference.map、 Reference.odx （orchestration 文件）、 \< *WebService*>.disco (发现文件），和\< *WebService*> 到你的项目的.wsdl （Web 服务描述语言文件）。</span><span class="sxs-lookup"><span data-stu-id="0a869-105">When you add a Web reference to your project, BizTalk project creates an orchestration Web port type, Web message types, Reference.map (map file), Reference.odx (orchestration file), \<*WebService*>.disco (discovery file), and \<*WebService*>.wsdl (Web Service Description Language file) to your project.</span></span> <span data-ttu-id="0a869-106">如果 Web Services 描述语言 (WSDL) 文件包含架构 Web 消息类型，则 BizTalk 项目会向你的项目添加 Reference.xsd。</span><span class="sxs-lookup"><span data-stu-id="0a869-106">If your Web Service Description Language (WSDL) file contains schema Web message types, BizTalk project adds Reference.xsd to your project.</span></span>  
  
 <span data-ttu-id="0a869-107">Web 引用包括：</span><span class="sxs-lookup"><span data-stu-id="0a869-107">A Web reference includes:</span></span>  
  
-   <span data-ttu-id="0a869-108">Web Services 的统一资源定位符 (URL)。</span><span class="sxs-lookup"><span data-stu-id="0a869-108">A Universal Resource Locator (URL) for the Web service.</span></span>  
  
-   <span data-ttu-id="0a869-109">WSDL 文件，提供关于服务的信息，如可用方法、端口和消息类型等。</span><span class="sxs-lookup"><span data-stu-id="0a869-109">A WSDL file that offers information about the service such as available methods, ports, and message types.</span></span>  
  
-   <span data-ttu-id="0a869-110">引用映射 (Reference.map)。</span><span class="sxs-lookup"><span data-stu-id="0a869-110">A reference map (Reference.map).</span></span>  
  
 <span data-ttu-id="0a869-111">添加 Web 引用时，该 Web Services 的所有 Web 方法必须与 BizTalk Server 兼容。</span><span class="sxs-lookup"><span data-stu-id="0a869-111">When you add a Web reference, all the Web methods for that Web service must be compatible with BizTalk Server.</span></span> <span data-ttu-id="0a869-112">不能为 Web Services 中的特定 Web 方法指定条件属性。</span><span class="sxs-lookup"><span data-stu-id="0a869-112">You cannot specify conditional attributes for specific Web methods in a Web service.</span></span>  
  
 <span data-ttu-id="0a869-113">通过将添加到你的项目的 Web 引用**添加 Web 引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="0a869-113">You add a Web reference to your project by using the **Add Web Reference** dialog box.</span></span> <span data-ttu-id="0a869-114">有关如何添加 Web 引用的详细信息，请参阅[使用 Visual Studio](../core/using-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="0a869-114">For more information about adding Web references, see [Using Visual Studio](../core/using-visual-studio.md).</span></span>  
  
 <span data-ttu-id="0a869-115">如果你计划使用业务流程执行语言 (BPEL) 导出过程导出业务流程，则不能从现有的 BizTalk 项目引用 Web 引用。</span><span class="sxs-lookup"><span data-stu-id="0a869-115">If you are planning to export your orchestration using the Business Process Execution Language (BPEL) export process, you cannot reference a Web reference from an existing BizTalk project.</span></span> <span data-ttu-id="0a869-116">如果从现有的 BizTalk 项目引用 Web 引用，BPEL 导出过程将自动生成第二个 WSDL 文件，并且将会丢失绑定信息。</span><span class="sxs-lookup"><span data-stu-id="0a869-116">When you reference a Web reference from an existing BizTalk project, the BPEL export process will auto-generate a second WSDL file and you will lose your binding information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a869-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a869-117">See Also</span></span>  
 <span data-ttu-id="0a869-118">[创建 Web 端口](../core/creating-web-ports.md) </span><span class="sxs-lookup"><span data-stu-id="0a869-118">[Creating Web Ports](../core/creating-web-ports.md) </span></span>  
 [<span data-ttu-id="0a869-119">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="0a869-119">Consuming Web Services</span></span>](../core/consuming-web-services.md)