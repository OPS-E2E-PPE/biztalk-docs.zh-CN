---
title: "限制在配置文件适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], restrictions
- File adapters, restrictions
ms.assetid: 8d8137a7-5b16-4ae3-a0a7-6d114324bdf3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6fbf9296e56db816277f9a7a348377bfa4b359d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="restrictions-when-configuring-the-file-adapter"></a><span data-ttu-id="5632e-102">配置文件适配器时的限制</span><span class="sxs-lookup"><span data-stu-id="5632e-102">Restrictions when configuring the File adapter</span></span>
<span data-ttu-id="5632e-103">限制和规则时使用的文件适配器。</span><span class="sxs-lookup"><span data-stu-id="5632e-103">Restrictions and rules when using the file adapter.</span></span>

## <a name="file-mask-and-file-name-gotchas"></a><span data-ttu-id="5632e-104">文件掩码和文件名称陷阱</span><span class="sxs-lookup"><span data-stu-id="5632e-104">File mask and file name gotchas</span></span>

<span data-ttu-id="5632e-105">文件掩码是一个字符串，用于指定文件接收处理程序将从接收位置提取的文件的类型。</span><span class="sxs-lookup"><span data-stu-id="5632e-105">The file mask is a string that specifies the type of file that the File receive handler will pick up from the receive location.</span></span> <span data-ttu-id="5632e-106">文件名是一个字符串，用于指定文件发送处理程序将在其中写入消息的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="5632e-106">The file name is a string that specifies the name of the file where the File send handler will write the message.</span></span>  
  
 <span data-ttu-id="5632e-107">文件名和文件掩码属性具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="5632e-107">The following restrictions apply to the file name and file mask properties:</span></span>  
  
-   <span data-ttu-id="5632e-108">每个接收位置或发送端口只能指定一个文件掩码或文件名。</span><span class="sxs-lookup"><span data-stu-id="5632e-108">Only one file mask or file name can be specified per receive location or send port.</span></span>  
  
-   <span data-ttu-id="5632e-109">不允许将完整路径或部分路径与文件掩码或文件名一起使用。</span><span class="sxs-lookup"><span data-stu-id="5632e-109">The full path or part of the path along with the file mask or file name is not allowed.</span></span> <span data-ttu-id="5632e-110">文件掩码和文件名始终表示不带路径的名称。</span><span class="sxs-lookup"><span data-stu-id="5632e-110">The file mask and file name always represent a name without the path.</span></span>  
  
-   <span data-ttu-id="5632e-111">文件掩码和文件名不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="5632e-111">The file mask and file name are not case-sensitive.</span></span>  
  
-   <span data-ttu-id="5632e-112">文件名称不能包含任何以下字符： \< \> : / &#124;" ?</span><span class="sxs-lookup"><span data-stu-id="5632e-112">The file name cannot contain any of the following characters: \< \> : / &#124; " ?</span></span> <span data-ttu-id="5632e-113">* ;</span><span class="sxs-lookup"><span data-stu-id="5632e-113">* ;</span></span>  
  
-   <span data-ttu-id="5632e-114">文件掩码不能包含任何以下字符： \< \> : / &#124;" ;</span><span class="sxs-lookup"><span data-stu-id="5632e-114">The file mask cannot contain any of the following characters: \< \> : / &#124; " ;</span></span> 
  
-   <span data-ttu-id="5632e-115">以下保留的设备名称不能作为文件的名称： CON、 PRN、 AUX、 时钟 $、 NUL、 COM1、 COM2、 COM3、 COM4、 COM5、 COM6、 COM7、 COM8、 COM9、 LPT1、 LPT2、 LPT3、 LPT4、 LPT5、 LPT6、 LPT7、 LPT8 和 LPT9。</span><span class="sxs-lookup"><span data-stu-id="5632e-115">The following reserved device names cannot be used as the name of a file: CON, PRN, AUX, CLOCK$, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, and LPT9.</span></span> <span data-ttu-id="5632e-116">此外，不允许使用这些保留名称与扩展名的任意组合。</span><span class="sxs-lookup"><span data-stu-id="5632e-116">In addition, any combinations of these with extensions are not allowed.</span></span>  
  
-   <span data-ttu-id="5632e-117">Windows 磁盘卷使用 8.3 （8.3 文件名） 默认情况下，使用短期和长期的文件的名称命名约定。</span><span class="sxs-lookup"><span data-stu-id="5632e-117">Windows disk volumes use the 8.3 (8dot3) naming convention by default, which uses short and long file names.</span></span> <span data-ttu-id="5632e-118">非系统磁盘卷禁用 8.3 文件名命名约定，并且因此仅使用长文件名。</span><span class="sxs-lookup"><span data-stu-id="5632e-118">Non-system disk volumes disable the 8dot3 naming convention, and therefore only use long file names.</span></span> 

    <span data-ttu-id="5632e-119">启用 8.3 文件名后，文件和其文件扩展名地转换为短名称。</span><span class="sxs-lookup"><span data-stu-id="5632e-119">When 8dot3 is enabled, files and their file extensions get converted to a short name.</span></span> <span data-ttu-id="5632e-120">例如，`testabcdefgh.docx`获取转换为`testab~1.doc`。</span><span class="sxs-lookup"><span data-stu-id="5632e-120">For example, `testabcdefgh.docx` gets converted to `testab~1.doc`.</span></span> <span data-ttu-id="5632e-121">请注意，将缩短文件名，并且文件扩展名将缩短从`.docx`到`doc`。</span><span class="sxs-lookup"><span data-stu-id="5632e-121">Notice that file name is shortened, and the file extension is shortened from `.docx` to `doc`.</span></span>

    <span data-ttu-id="5632e-122">此行为会影响如何文件适配器接收文件。</span><span class="sxs-lookup"><span data-stu-id="5632e-122">This behavior impacts how the File adapter receives file.</span></span> <span data-ttu-id="5632e-123">如果文件掩码设置为`*.xml`，然后文件匹配同时`*.xml`和`*.xmln`选取扩展。</span><span class="sxs-lookup"><span data-stu-id="5632e-123">If a file mask is set to `*.xml`, then files matching both `*.xml` and `*.xmln` extensions are picked up.</span></span> 

    <span data-ttu-id="5632e-124">若要查看是否对你的磁盘启用了 8.3 文件名命名约定，打开命令提示符，作为管理员，并键入`fsutil 8dot3name query c:`，或`fsutil 8dot3name query d:`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="5632e-124">To see if the 8dot3 naming convention is enabled on your disks, open a command prompt as Administrator, and type `fsutil 8dot3name query c:`, or `fsutil 8dot3name query d:`, and so on.</span></span> <span data-ttu-id="5632e-125">示例输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="5632e-125">Sample output looks like the following:</span></span>

    ```
    C:\WINDOWS\system32>fsutil 8dot3name query c:
    The volume state is: 0 (8dot3 name creation is enabled).
    The registry state is: 2 (Per volume setting - the default).
    
    Based on the above two settings, 8dot3 name creation is enabled on c:
    ```
    
    <span data-ttu-id="5632e-126">文件适配器使用[FindFirstFile 函数](https://msdn.microsoft.com/library/windows/desktop/aa364418(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="5632e-126">The File adapter uses the [FindFirstFile function](https://msdn.microsoft.com/library/windows/desktop/aa364418(v=vs.85).aspx).</span></span> <span data-ttu-id="5632e-127">此函数包括具有短期和长期的文件名的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5632e-127">This function includes search results that have the short and long file names.</span></span> <span data-ttu-id="5632e-128">若要查看的短期和长期的文件名称的文件夹中，打开命令提示符处，转到文件夹，然后键入`dir /x`。</span><span class="sxs-lookup"><span data-stu-id="5632e-128">To see the short and long file names in a folder, open a command prompt, go to your folder, and type `dir /x`.</span></span> <span data-ttu-id="5632e-129">在命令提示符下，你可以键入`dir c:\foldername /x`。</span><span class="sxs-lookup"><span data-stu-id="5632e-129">In a command prompt, you can also type `dir c:\foldername /x`.</span></span>
    
    <span data-ttu-id="5632e-130">如果你更改 8dot3name 设置的卷上，新的文件将使用新的设置。</span><span class="sxs-lookup"><span data-stu-id="5632e-130">If you change the 8dot3name setting on a volume, then new files use the new setting.</span></span> <span data-ttu-id="5632e-131">直到将它们移动，任何现有文件将保留其名称。</span><span class="sxs-lookup"><span data-stu-id="5632e-131">Any existing files keep their names until they are moved.</span></span> 
    
    <span data-ttu-id="5632e-132">若要仅选取你预期的文件，并在更高版本的加载过程中获得更好的性能 （开销较低），则可能为最佳配置文件适配器，以使用卷其中 8dot3name 处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="5632e-132">To only pick up your intended files, and to get better performance (less overhead) during higher load, then it may be best to configure the File adapter to use a volume where 8dot3name is disabled.</span></span> 
  
-   <span data-ttu-id="5632e-133">文件路径、文件掩码和文件名（没有宏替换）的总长度不能超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="5632e-133">The total length of the file path, file mask, and file name (without macro substitution) must not exceed 256 characters.</span></span> <span data-ttu-id="5632e-134">（这是 MessageBox 数据库的限制。）</span><span class="sxs-lookup"><span data-stu-id="5632e-134">(This is a restriction of the MessageBox database.)</span></span>  
  
-   <span data-ttu-id="5632e-135">文件路径不能以“`\\`?”开头。</span><span class="sxs-lookup"><span data-stu-id="5632e-135">The file path cannot begin with "`\\`?".</span></span>  
  
-   <span data-ttu-id="5632e-136">网络映射驱动器号不能用在文件路径中，因为它们是基于用户会话的。</span><span class="sxs-lookup"><span data-stu-id="5632e-136">Mapped network drive letters cannot be used in the file path, because they are user session based.</span></span>  
  
 <span data-ttu-id="5632e-137">BizTalk 消息引擎在设计时始终通过使用前面列出的项来验证文件名和文件掩码属性。</span><span class="sxs-lookup"><span data-stu-id="5632e-137">The BizTalk Messaging Engine always validates the file name and file mask properties at design time by using the items previously listed.</span></span> <span data-ttu-id="5632e-138">此外，如果适配器在动态端口上发送消息，则文件适配器将在运行时验证文件名和文件掩码属性。</span><span class="sxs-lookup"><span data-stu-id="5632e-138">In addition, the File adapter validates the file name and file mask properties at run time if the adapter sends the message on a dynamic port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5632e-139">文件适配器不提取系统文件或只读文件。</span><span class="sxs-lookup"><span data-stu-id="5632e-139">The File adapter does not pick up system files or read-only files.</span></span> <span data-ttu-id="5632e-140">只提取基于磁盘的文件，而不提取设备文件。</span><span class="sxs-lookup"><span data-stu-id="5632e-140">Only disk-based files are picked up, and not device files.</span></span>  

## <a name="using-macros-in-file-names"></a><span data-ttu-id="5632e-141">在文件名中使用宏</span><span class="sxs-lookup"><span data-stu-id="5632e-141">Using macros in file names</span></span>

<span data-ttu-id="5632e-142">您可以使用预定义的宏集合动态创建文件发送处理程序在其中写入消息的文件。</span><span class="sxs-lookup"><span data-stu-id="5632e-142">You can use a predefined set of macros to dynamically create the files in which the File send handler writes messages.</span></span> <span data-ttu-id="5632e-143">在文件系统中创建文件之前，文件发送处理程序将使用单独的值来替换文件名中的所有宏。</span><span class="sxs-lookup"><span data-stu-id="5632e-143">Before creating a file on the file system, the File send handler replaces all the macros in the file name with their individual values.</span></span> <span data-ttu-id="5632e-144">可以在一个文件名中使用若干不同的宏。</span><span class="sxs-lookup"><span data-stu-id="5632e-144">You can use several different macros in one file name.</span></span>  
  
 <span data-ttu-id="5632e-145">在使用 BizTalk 浏览器对象模型配置文件发送处理程序时，可以使用文件名宏。</span><span class="sxs-lookup"><span data-stu-id="5632e-145">You can use the file name macros while configuring the File send handler using the BizTalk Explorer object model.</span></span>  
  
 <span data-ttu-id="5632e-146">如果存在以下任何一种情况，文件发送处理程序将不会使用值替换宏：</span><span class="sxs-lookup"><span data-stu-id="5632e-146">The File send handler does not replace the macros with a value if any of the following are true:</span></span>  
  
-   <span data-ttu-id="5632e-147">未设置相应的系统属性。</span><span class="sxs-lookup"><span data-stu-id="5632e-147">The corresponding system property is not set.</span></span>  
  
-   <span data-ttu-id="5632e-148">宏拼写错误。</span><span class="sxs-lookup"><span data-stu-id="5632e-148">The macro is misspelled.</span></span>  
  
-   <span data-ttu-id="5632e-149">宏的值所包含的符号在文件名中无效。</span><span class="sxs-lookup"><span data-stu-id="5632e-149">The value for the macro contains symbols that are not valid in the file name.</span></span>  
  
 <span data-ttu-id="5632e-150">如果出现上述任何情况，文件发送处理程序都会将文件名中的宏保持不变，例如 Myfile_%MessageID%.xml。</span><span class="sxs-lookup"><span data-stu-id="5632e-150">If any of these conditions occur, the File send handler leaves the macros in the file name untouched, for example Myfile_%MessageID%.xml.</span></span>  
  
 <span data-ttu-id="5632e-151">下表列出了所支持的宏，并介绍文件发送处理程序如何替换这些宏：</span><span class="sxs-lookup"><span data-stu-id="5632e-151">The following table lists the supported macros and describes how the File send handler replaces them.</span></span>  
  
|<span data-ttu-id="5632e-152">宏名称</span><span class="sxs-lookup"><span data-stu-id="5632e-152">Macro name</span></span>|<span data-ttu-id="5632e-153">替代值</span><span class="sxs-lookup"><span data-stu-id="5632e-153">Substitute value</span></span>|  
|----------------|----------------------|  
|<span data-ttu-id="5632e-154">%datetime%</span><span class="sxs-lookup"><span data-stu-id="5632e-154">%datetime%</span></span>|<span data-ttu-id="5632e-155">YYYY-MM-DDThhmmss 格式的世界时 (UTC) 日期时间（例如 1997-07-12T103508）。</span><span class="sxs-lookup"><span data-stu-id="5632e-155">Coordinated Universal Time (UTC) date time in the format YYYY-MM-DDThhmmss (for example, 1997-07-12T103508).</span></span>|  
|<span data-ttu-id="5632e-156">%datetime_bts2000%</span><span class="sxs-lookup"><span data-stu-id="5632e-156">%datetime_bts2000%</span></span>|<span data-ttu-id="5632e-157">YYYYMMDDhhmmsss 格式的 UTC 日期时间，其中，sss 表示秒和毫秒（例如，199707121035234 表示 1997/07/12 10:35:23 和 400 毫秒）。</span><span class="sxs-lookup"><span data-stu-id="5632e-157">UTC date time in the format YYYYMMDDhhmmsss, where sss means seconds and milliseconds (for example, 199707121035234 means 1997/07/12, 10:35:23 and 400 milliseconds).</span></span>|  
|<span data-ttu-id="5632e-158">%datetime.tz%</span><span class="sxs-lookup"><span data-stu-id="5632e-158">%datetime.tz%</span></span>|<span data-ttu-id="5632e-159">本地日期时间加上 GMT 时区，格式为 YYYY-MM-DDThhmmssTZD（例如 1997-07-12T103508+800）。</span><span class="sxs-lookup"><span data-stu-id="5632e-159">Local date time plus time zone from GMT in the format YYYY-MM-DDThhmmssTZD, (for example, 1997-07-12T103508+800).</span></span>|  
|<span data-ttu-id="5632e-160">%DestinationParty%</span><span class="sxs-lookup"><span data-stu-id="5632e-160">%DestinationParty%</span></span>|<span data-ttu-id="5632e-161">目标参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="5632e-161">Name of the destination party.</span></span> <span data-ttu-id="5632e-162">该值来自消息上下文属性 **BTS.DestinationParty**。</span><span class="sxs-lookup"><span data-stu-id="5632e-162">The value comes from the message context property **BTS.DestinationParty**.</span></span>|  
|<span data-ttu-id="5632e-163">%DestinationPartyQualifier%</span><span class="sxs-lookup"><span data-stu-id="5632e-163">%DestinationPartyQualifier%</span></span>|<span data-ttu-id="5632e-164">目标参与方的限定符。</span><span class="sxs-lookup"><span data-stu-id="5632e-164">Qualifier of the destination party.</span></span> <span data-ttu-id="5632e-165">该值来自消息上下文属性 **BTS.DestinationPartyQualifier**。</span><span class="sxs-lookup"><span data-stu-id="5632e-165">The value comes from the message context property **BTS.DestinationPartyQualifier**.</span></span>|  
|<span data-ttu-id="5632e-166">%MessageID%</span><span class="sxs-lookup"><span data-stu-id="5632e-166">%MessageID%</span></span>|<span data-ttu-id="5632e-167">BizTalk Server 中消息的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="5632e-167">Globally unique identifier (GUID) of the message in BizTalk Server.</span></span> <span data-ttu-id="5632e-168">值直接来自消息上下文属性**BTS。MessageID**。</span><span class="sxs-lookup"><span data-stu-id="5632e-168">The value comes directly from the message context property **BTS.MessageID**.</span></span>|  
|<span data-ttu-id="5632e-169">%SourceFileName%</span><span class="sxs-lookup"><span data-stu-id="5632e-169">%SourceFileName%</span></span>|<span data-ttu-id="5632e-170">文件适配器从中读取消息的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="5632e-170">Name of the file from which the File adapter read the message.</span></span> <span data-ttu-id="5632e-171">文件名称包括扩展名，并排除的文件路径，例如，Sample.xml。</span><span class="sxs-lookup"><span data-stu-id="5632e-171">The file name includes the extension and excludes the file path, for example, Sample.xml.</span></span> <span data-ttu-id="5632e-172">文件适配器时替换此属性，从存储中的绝对文件路径中提取的文件名称**文件。ReceivedFileName**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="5632e-172">When substituting this property, the File adapter extracts the file name from the absolute file path stored in the **FILE.ReceivedFileName** context property.</span></span> <span data-ttu-id="5632e-173">如果上下文属性不具有值-例如，如果而不是文件适配器适配器上接收的消息 — 宏将不会替换，并且将保持原样的文件名称中 (例如，C:\Drop\\%sourcefilename%)。</span><span class="sxs-lookup"><span data-stu-id="5632e-173">If the context property does not have a value—for example, if a message was received on an adapter other than the File adapter—the macro will not be substituted and will remain in the file name as is (for example, C:\Drop\\%SourceFileName%).</span></span> <span data-ttu-id="5632e-174">**注意：**此宏的正确实现需要输出消息是作为对收到的消息，同一消息。</span><span class="sxs-lookup"><span data-stu-id="5632e-174">**Note:**  Correct implementation of this macro requires that the output message is the same message as the received message.</span></span>|  
|<span data-ttu-id="5632e-175">%SourceParty%</span><span class="sxs-lookup"><span data-stu-id="5632e-175">%SourceParty%</span></span>|<span data-ttu-id="5632e-176">文件适配器从其接收消息的源参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="5632e-176">Name of the source party from which the File adapter received the message.</span></span> <span data-ttu-id="5632e-177">**注意：**此宏的正确实现需要输出消息是作为对收到的消息，同一消息。</span><span class="sxs-lookup"><span data-stu-id="5632e-177">**Note:**  Correct implementation of this macro requires that the output message is the same message as the received message.</span></span>|  
|<span data-ttu-id="5632e-178">%SourcePartyQualifier%</span><span class="sxs-lookup"><span data-stu-id="5632e-178">%SourcePartyQualifier%</span></span>|<span data-ttu-id="5632e-179">文件适配器从其接收消息的源参与方的限定符。</span><span class="sxs-lookup"><span data-stu-id="5632e-179">Qualifier of the source party from which the File adapter received the message.</span></span> <span data-ttu-id="5632e-180">**注意：**此宏的正确实现需要输出消息是作为对收到的消息，同一消息。</span><span class="sxs-lookup"><span data-stu-id="5632e-180">**Note:**  Correct implementation of this macro requires that the output message is the same message as the received message.</span></span>|  
|<span data-ttu-id="5632e-181">%time%</span><span class="sxs-lookup"><span data-stu-id="5632e-181">%time%</span></span>|<span data-ttu-id="5632e-182">hhmmss 格式的 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="5632e-182">UTC time in the format hhmmss.</span></span>|  
|<span data-ttu-id="5632e-183">%time.tz%</span><span class="sxs-lookup"><span data-stu-id="5632e-183">%time.tz%</span></span>|<span data-ttu-id="5632e-184">本地时间加上 GMT 时区，格式为 hhmmssTZD（例如 124525+530）。</span><span class="sxs-lookup"><span data-stu-id="5632e-184">Local time plus time zone from GMT in the format hhmmssTZD (for example, 124525+530).</span></span>|  
  
 
## <a name="receive-folder-and-destination-location-properties-gotchas"></a><span data-ttu-id="5632e-185">接收文件夹和目标位置属性陷阱</span><span class="sxs-lookup"><span data-stu-id="5632e-185">Receive folder and destination location properties gotchas</span></span>

<span data-ttu-id="5632e-186">文件接收位置字符串包含指向文件接收处理程序从中读取文件的文件系统或网络共享位置上文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="5632e-186">The file receive location is a string that contains a path to a folder on a file system or network share from which the File receive handler reads files.</span></span> <span data-ttu-id="5632e-187">文件目标位置字符串包含指向文件发送处理程序要向其中写入文件的文件系统或网络共享位置上文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="5632e-187">The file destination location is a string that contains a path to a folder on a file system or network share where the File send handler writes files.</span></span>  
  
 <span data-ttu-id="5632e-188">接收文件夹和目标位置属性具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="5632e-188">The following restrictions apply to the receive folder and destination location properties:</span></span>  
  
-   <span data-ttu-id="5632e-189">当在用户指定属性时则不需要的文件系统或网络共享上的文件路径存在。</span><span class="sxs-lookup"><span data-stu-id="5632e-189">Existence of the file path on a file system or network share is not required at the time when you specify the property in the user.</span></span>  
  
-   <span data-ttu-id="5632e-190">文件路径始终必须是绝对路径。</span><span class="sxs-lookup"><span data-stu-id="5632e-190">The file path must always be absolute.</span></span>  
  
-   <span data-ttu-id="5632e-191">你可以使用通用命名约定 (UNC) 格式指定的文件路径 (例如， \\ \\ <*服务器*\> \\ < *共享*\>)。</span><span class="sxs-lookup"><span data-stu-id="5632e-191">You can specify the file path by using Universal Naming Convention (UNC) format (for example, \\\\<*server*\>\\<*share*\>).</span></span>  
  
-   <span data-ttu-id="5632e-192">如果该文件路径是 UNC 格式，服务器名称不得包含以下字符: ' ~ ！</span><span class="sxs-lookup"><span data-stu-id="5632e-192">If the file path is in UNC format, the server name must not contain the following characters: \` ~ !</span></span> <span data-ttu-id="5632e-193">@ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< \> / ?</span><span class="sxs-lookup"><span data-stu-id="5632e-193">@ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< \> / ?</span></span> <span data-ttu-id="5632e-194">;</span><span class="sxs-lookup"><span data-stu-id="5632e-194">;</span></span>  
  
-   <span data-ttu-id="5632e-195">不能使用父 (\\...\\) 和当前 (\\。\\) 文件夹中的文件路径的任何部分的符号。</span><span class="sxs-lookup"><span data-stu-id="5632e-195">You cannot use parent (\\..\\) and current (\\.\\) folder symbols in any part of the file path.</span></span>  
  
-   <span data-ttu-id="5632e-196">文件路径不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="5632e-196">The file path is not case-sensitive.</span></span>  
  
-   <span data-ttu-id="5632e-197">文件路径不能包含任何以下字符： \< \> : / &#124;" ?</span><span class="sxs-lookup"><span data-stu-id="5632e-197">The file path cannot contain any of the following characters: \< \> : / &#124; " ?</span></span> <span data-ttu-id="5632e-198">* ;</span><span class="sxs-lookup"><span data-stu-id="5632e-198">* ;</span></span>  
  
-   <span data-ttu-id="5632e-199">在文件路径中不能使用以下保留的设备名称：CON、PRN、AUX、CLOCK$、NUL、COM1、COM2、COM3、COM4、COM5、COM6、COM7、COM8、COM9、LPT1、LPT2、LPT3、LPT4、LPT5、LPT6、LPT7、LPT8 和 LPT9。</span><span class="sxs-lookup"><span data-stu-id="5632e-199">You cannot use the following reserved device names in the file path: CON, PRN, AUX, CLOCK$, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, and LPT9.</span></span>  
  
-   <span data-ttu-id="5632e-200">文件路径、文件掩码或文件名（没有宏替换）的总长度不能超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="5632e-200">Total length of file path, file mask, or file name (without macro substitution) must not exceed 256 characters.</span></span> <span data-ttu-id="5632e-201">（MessageBox 数据库规定了此限制。）</span><span class="sxs-lookup"><span data-stu-id="5632e-201">(The MessageBox database imposes this restriction.)</span></span>  
  
-   <span data-ttu-id="5632e-202">文件适配器不支持 Unicode 规范的文件路径 (例如，"\\\\？\\")。</span><span class="sxs-lookup"><span data-stu-id="5632e-202">The File adapter does not support Unicode specification of the file path (for example, "\\\\?\\").</span></span>  
  
 <span data-ttu-id="5632e-203">以下限制只适用于接收文件夹属性：</span><span class="sxs-lookup"><span data-stu-id="5632e-203">Restrictions on the receive folder property only:</span></span>  
  
-   <span data-ttu-id="5632e-204">请不要将接收文件夹属性设置为使用 Microsoft Windows NT 分布式文件系统的带符号链接的文件夹 。</span><span class="sxs-lookup"><span data-stu-id="5632e-204">Do not set the receive folder property to a folder that uses the Microsoft Windows NT Distributed File System with a symbolic link.</span></span> <span data-ttu-id="5632e-205">如果使用 Windows NT 分布式文件系统 ， 则在文件适配器接收位置中只能使用具有直接网络路径的文件夹 。</span><span class="sxs-lookup"><span data-stu-id="5632e-205">If you are using Windows NT Distributed File System, you can only use folders with straight network paths in File adapter receive locations.</span></span>  
  
-   <span data-ttu-id="5632e-206">如果将文档发送到 UNC 路径，并且有多台服务器通过文件适配器的接收位置接收文档，则只有一台服务器将提取并处理发送到该 UNC 路径的大多数文档。</span><span class="sxs-lookup"><span data-stu-id="5632e-206">When documents are sent to a UNC path, and you have more than one server receiving documents at the receive location for the File adapter, only one server will pick up and process most of the documents sent to that UNC path.</span></span> <span data-ttu-id="5632e-207">有关重命名文件的详细信息，请参阅的文件接收适配器部分[文件适配器](../core/file-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5632e-207">For more information about file renaming, see the File Receive Adapter section of [File Adapter](../core/file-adapter.md).</span></span>  
  
 <span data-ttu-id="5632e-208">以下限制只适用于发送文件夹属性：</span><span class="sxs-lookup"><span data-stu-id="5632e-208">Restrictions on the send folder property only:</span></span>  
  
-   <span data-ttu-id="5632e-209">文件适配器可能没有足够的操作系统资源来处理所有批处理中的消息，同时在非服务器操作系统如 Microsoft Windows Vista 上运行时。</span><span class="sxs-lookup"><span data-stu-id="5632e-209">The file adapter may not have enough operating system resources to process all of the messages in a batch concurrently when running on a non-server operating system like Microsoft Windows Vista.</span></span>  
  
 <span data-ttu-id="5632e-210">文件适配器将在设计时通过使用上文所述的规则对文件路径进行验证。</span><span class="sxs-lookup"><span data-stu-id="5632e-210">The File adapter validates the file path at design time by using the previously mentioned rules.</span></span> <span data-ttu-id="5632e-211">此外，如果文件适配器通过动态端口发送消息，还会在运行时对消息进行验证。</span><span class="sxs-lookup"><span data-stu-id="5632e-211">In addition, the File adapter validates the message at run time if the adapter sends the message through a dynamic port with a File adapter.</span></span>  
  
