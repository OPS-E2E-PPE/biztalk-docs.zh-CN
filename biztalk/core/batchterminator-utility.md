---
title: BatchTerminator 实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 771241fa-7df5-4882-8430-c2f36200cc9d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e64c14cc2c1ff7538f96275bb452f0ef643327c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358253"
---
# <a name="batchterminator-utility"></a><span data-ttu-id="1aa49-102">BatchTerminator 实用工具</span><span class="sxs-lookup"><span data-stu-id="1aa49-102">BatchTerminator Utility</span></span>
<span data-ttu-id="1aa49-103">BatchTerminator 实用工具，可终止所有的批处理业务流程用于批量处理 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="1aa49-103">The BatchTerminator utility enables you to terminate all live batching orchestrations being used to batch EDI interchanges.</span></span> <span data-ttu-id="1aa49-104">如果有大量的批处理业务流程实例运行，并且需要终止所有批处理，以便 BizTalk server 系统上执行维护，此实用工具将非常有用。</span><span class="sxs-lookup"><span data-stu-id="1aa49-104">This utility could prove useful if you have a large number of batching orchestration instances running, and you need to terminate all the batches in order to perform maintenance on the BizTalk server system.</span></span>  
  
 <span data-ttu-id="1aa49-105">BatchTerminator 实用工具位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1aa49-105">The BatchTerminator utility is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator folder.</span></span> <span data-ttu-id="1aa49-106">当您运行此实用工具以终止批处理业务流程实例时，该实用工具会将结果记录的 batchterminator.log 文件中\<*驱动器*\>: \Documents and 设置\\<*用户名*\>\Application Data 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1aa49-106">When you run the utility to terminate the batching orchestration instances, the utility will log the results in the batchterminator.log file in the \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1aa49-107">32 位系统才支持 BatchTerminator 实用工具。</span><span class="sxs-lookup"><span data-stu-id="1aa49-107">The BatchTerminator utility is only supported on 32 bit systems.</span></span>  <span data-ttu-id="1aa49-108">BatchTerminator 使用 Microsoft.BizTalk.ExplorerOM 命名空间，它才支持使用从 32 位进程中的组件。</span><span class="sxs-lookup"><span data-stu-id="1aa49-108">BatchTerminator uses components in the Microsoft.BizTalk.ExplorerOM namespace, which is only supported if used from a 32 bit process.</span></span>  
  
 <span data-ttu-id="1aa49-109">**重新启动终止的业务流程实例**</span><span class="sxs-lookup"><span data-stu-id="1aa49-109">**Restarting the Terminated Orchestration Instances**</span></span>  
  
 <span data-ttu-id="1aa49-110">终止批处理业务流程的一组后，可以执行这些业务流程实例的批量重新启动。</span><span class="sxs-lookup"><span data-stu-id="1aa49-110">After you terminate a group of batching orchestrations, you can do a bulk restart of those orchestration instances.</span></span> <span data-ttu-id="1aa49-111">请使用 /Activate 开关的名称和指示被停止批处理文件的路径。</span><span class="sxs-lookup"><span data-stu-id="1aa49-111">You do so with the /Activate switch and the name and path of a file that indicates the batches that were stopped.</span></span> <span data-ttu-id="1aa49-112">当您运行该实用工具终止一组业务流程实例时，该实用程序将创建此停止批处理文件。</span><span class="sxs-lookup"><span data-stu-id="1aa49-112">When you run the utility to terminate a group of orchestration instances, the utility will create this stopped-batches file.</span></span> <span data-ttu-id="1aa49-113">停止批处理文件为 batchSettings-\<GUID\>中的.xml \<*驱动器*\>: \Documents and 设置\\<*用户名* \>\Application data 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1aa49-113">The stopped-batches file is batchSettings-\<GUID\>.xml in the \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder.</span></span> <span data-ttu-id="1aa49-114">路径和停止批处理文件的名称也保存在日志文件。</span><span class="sxs-lookup"><span data-stu-id="1aa49-114">The path and name of the stopped-batches file is also saved in the log file.</span></span> <span data-ttu-id="1aa49-115">该实用工具使用的运行时 / 激活开关，它会验证根据架构对输入的文件。</span><span class="sxs-lookup"><span data-stu-id="1aa49-115">When the utility runs with the /activate switch, it validates the input file against a schema.</span></span>  
  
 <span data-ttu-id="1aa49-116">**语法**</span><span class="sxs-lookup"><span data-stu-id="1aa49-116">**Syntax**</span></span>  
  
 <span data-ttu-id="1aa49-117">使用以下语法的命令行窗口中运行 BatchTerminator 实用工具：</span><span class="sxs-lookup"><span data-stu-id="1aa49-117">Run the BatchTerminator utility in a command-line window with the following syntax:</span></span>  
  
```  
BatchTerminator /<switch>  
```  
  
 <span data-ttu-id="1aa49-118">可以使用以下开关运行 BatchTerminator 实用工具。</span><span class="sxs-lookup"><span data-stu-id="1aa49-118">You can run the BatchTerminator utility with the following switches.</span></span> <span data-ttu-id="1aa49-119">如果未不提供任何开关，终止 / 使用选项。</span><span class="sxs-lookup"><span data-stu-id="1aa49-119">If no switch is provided, the /terminate option is used.</span></span> <span data-ttu-id="1aa49-120">如下所示，您可以输入开关的完整名称，例如 / 终止，或使用缩写形式，在这种情况下，/t。</span><span class="sxs-lookup"><span data-stu-id="1aa49-120">As indicate below, you can enter the full name of the switch, such as /terminate, or the shortened form, in this case, /t.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1aa49-121">开关</span><span class="sxs-lookup"><span data-stu-id="1aa49-121">Switch</span></span>|<span data-ttu-id="1aa49-122">函数</span><span class="sxs-lookup"><span data-stu-id="1aa49-122">Function</span></span>|  
|<span data-ttu-id="1aa49-123">/?</span><span class="sxs-lookup"><span data-stu-id="1aa49-123">/?</span></span>|<span data-ttu-id="1aa49-124">显示帮助</span><span class="sxs-lookup"><span data-stu-id="1aa49-124">Displays help</span></span>|  
|<span data-ttu-id="1aa49-125">/ 终止-log:\<*日志文件*\></span><span class="sxs-lookup"><span data-stu-id="1aa49-125">/terminate -log:\<*log file*\></span></span><br /><br /> <span data-ttu-id="1aa49-126">或 /t-log:\<*日志文件*\></span><span class="sxs-lookup"><span data-stu-id="1aa49-126">or /t -log:\<*log file*\></span></span>|<span data-ttu-id="1aa49-127">发送终止控制消息向所有活动的 X12 或 EDIFACT 批处理业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="1aa49-127">Sends terminate control messages to all active X12 or EDIFACT batching orchestration instances.</span></span> <span data-ttu-id="1aa49-128">它将显示该操作，包括它终止的所有活动批处理业务流程实例的列表、 活动批处理业务流程所找到的数量和它所发送的终止控制消息数的结果。</span><span class="sxs-lookup"><span data-stu-id="1aa49-128">It displays the results of the operation, including a list of all active batch orchestration instances that it terminated, the number of active batch orchestrations that it found, and the number of terminate control messages that it sent.</span></span> <span data-ttu-id="1aa49-129">它将结果记录到的 batchterminator.log 文件中\<*驱动器*\>: \Documents and 设置\\<*用户名*\>\应用程序数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="1aa49-129">It logs the results into the batchterminator.log file in the \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder.</span></span><br /><br /> <span data-ttu-id="1aa49-130">选择的 – log： 参数使你可以指定日志文件的名称和/或你想要保存到的日志文件的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="1aa49-130">The optional -log: parameter enables you to specify the name of the log file and/or the path of the folder that you want the log file to be saved to.</span></span> <span data-ttu-id="1aa49-131">使用参数来指定的路径和文件名称的一个示例是以下： `BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`。</span><span class="sxs-lookup"><span data-stu-id="1aa49-131">An example of using the parameter to specify the path and file name is the following: `BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`.</span></span> <span data-ttu-id="1aa49-132">使用参数来指定文件名称的示例只是以下： `BatchTerminator.exe /terminate -log:log.txt`。</span><span class="sxs-lookup"><span data-stu-id="1aa49-132">An example of using the parameter to specify the file name only is the following: `BatchTerminator.exe /terminate -log:log.txt`.</span></span> <span data-ttu-id="1aa49-133">如果指定的路径无效，该实用工具将使用默认路径： \<*驱动器*\>: \Documents and 设置\\<*用户名*\>\Application 数据。</span><span class="sxs-lookup"><span data-stu-id="1aa49-133">If the path specified is invalid, the utility will use the default path: \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data.</span></span> <span data-ttu-id="1aa49-134">-Log： 无论是否可以使用参数 /terminate 开关。</span><span class="sxs-lookup"><span data-stu-id="1aa49-134">The -log: parameter can be used either with or without the /terminate switch.</span></span>|  
|<span data-ttu-id="1aa49-135">/print</span><span class="sxs-lookup"><span data-stu-id="1aa49-135">/print</span></span><br /><br /> <span data-ttu-id="1aa49-136">or /p</span><span class="sxs-lookup"><span data-stu-id="1aa49-136">or /p</span></span>|<span data-ttu-id="1aa49-137">显示当前活动批处理业务流程实例的列表，不发送终止控制消息</span><span class="sxs-lookup"><span data-stu-id="1aa49-137">Displays a listing of the current active batching orchestration instances without sending terminate control messages</span></span>|  
|<span data-ttu-id="1aa49-138">/activate:\<*path*\>\\</span><span class="sxs-lookup"><span data-stu-id="1aa49-138">/activate:\<*path*\>\\</span></span><br /><span data-ttu-id="1aa49-139">batchSettings-\<*GUID*\>.xml-log:\<*日志文件*\></span><span class="sxs-lookup"><span data-stu-id="1aa49-139">batchSettings-\<*GUID*\>.xml -log:\<*log file*\></span></span><br /><br /> <span data-ttu-id="1aa49-140">或 /a:\<*路径*\>\\</span><span class="sxs-lookup"><span data-stu-id="1aa49-140">or /a:\<*path*\>\\</span></span><br /><span data-ttu-id="1aa49-141">batchSettings-\<*GUID*\>.xml-log:\<*日志文件*\></span><span class="sxs-lookup"><span data-stu-id="1aa49-141">batchSettings-\<*GUID*\>.xml -log:\<*log file*\></span></span>|<span data-ttu-id="1aa49-142">重新激活先前终止的业务流程实例中 batchSettings-列出\<GUID\>.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="1aa49-142">Reactivates the previously terminated orchestration instances that are listed in the batchSettings-\<GUID\>.xml file.</span></span> <span data-ttu-id="1aa49-143">该实用程序将验证根据代码中嵌入的架构对输入的文件。</span><span class="sxs-lookup"><span data-stu-id="1aa49-143">The utility will validate the input file against a schema embedded in the code.</span></span> <span data-ttu-id="1aa49-144">如果输入的文件与架构不匹配，将显示在屏幕上一条错误消息并退出程序。</span><span class="sxs-lookup"><span data-stu-id="1aa49-144">If the input file does not match the schema, an error message will be printed to the screen and the program will exit.</span></span><br /><br /> <span data-ttu-id="1aa49-145">此操作将有关重新启动操作的信息写入日志文件中如果包含-log： 开关。</span><span class="sxs-lookup"><span data-stu-id="1aa49-145">This operation writes information about the restarting action in the log file if you include the -log: switch.</span></span>|  
  
 <span data-ttu-id="1aa49-146">**批处理激活文件的格式**</span><span class="sxs-lookup"><span data-stu-id="1aa49-146">**Format of the Batch Activation File**</span></span>  
  
 <span data-ttu-id="1aa49-147">若要重新激活先前终止批处理业务流程实例使用 /activate 开关，必须提供批处理激活文件 (batchSettings-\<GUID\>.xml)。</span><span class="sxs-lookup"><span data-stu-id="1aa49-147">To reactivate previously terminated batch orchestration instances by using the /activate switch, you must provide a batch activation file (batchSettings-\<GUID\>.xml).</span></span> <span data-ttu-id="1aa49-148">此文件必须采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="1aa49-148">This file must be in the following format:</span></span>  
  
```  
<?xml version="1.0"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" elementFormDefault="qualified" id="BatchInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="BatchTerminator">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="Batch">  
          <xs:complexType>  
            <xs:attribute name="PartyName" type="xs:string" />  
            <xs:attribute name="PartyID" type="xs:int" use="required" />  
            <xs:attribute name=”BatchName” type=”xs:string” />  
            <xs:attribute name=”BatchID” type=”xs:int” use=”required” />  
            <xs:attribute name="EdiMessageType" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="prerequisites"></a><span data-ttu-id="1aa49-149">先决条件</span><span class="sxs-lookup"><span data-stu-id="1aa49-149">Prerequisites</span></span>  
 <span data-ttu-id="1aa49-150">以下是执行本主题中的过程的先决条件：</span><span class="sxs-lookup"><span data-stu-id="1aa49-150">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="1aa49-151">您必须以 BizTalk Server Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="1aa49-151">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-run-the-batchterminator-utility"></a><span data-ttu-id="1aa49-152">若要运行 BatchTerminator 实用工具</span><span class="sxs-lookup"><span data-stu-id="1aa49-152">To run the BatchTerminator utility</span></span>  
  
1. <span data-ttu-id="1aa49-153">在 Windows 资源管理器，转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1aa49-153">In Windows Explorer, move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator folder.</span></span>  
  
2. <span data-ttu-id="1aa49-154">Enter **BatchTerminator**，包括任何所需的开关，然后单击**Enter**。</span><span class="sxs-lookup"><span data-stu-id="1aa49-154">Enter **BatchTerminator**, including any desired switches, and then click **Enter**.</span></span>  
  
3. <span data-ttu-id="1aa49-155">在 Windows 资源管理器，转至\<*驱动器*\>: \Documents and 设置\\<*用户名*\>\Application Data 文件夹，并打开 batchterminator.log 文件以查看结果的日志。</span><span class="sxs-lookup"><span data-stu-id="1aa49-155">In Windows Explorer, move to \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder, and open the batchterminator.log file to see a log of the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa49-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="1aa49-156">See Also</span></span>  
 [<span data-ttu-id="1aa49-157">SDK 中的实用工具</span><span class="sxs-lookup"><span data-stu-id="1aa49-157">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)