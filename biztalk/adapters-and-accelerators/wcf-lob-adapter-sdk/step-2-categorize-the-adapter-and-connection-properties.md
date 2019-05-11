---
title: 第 2 步：适配器和连接属性进行分类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45b3dc64-2078-4008-878b-501f727f4a11
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d0d618d2e02e04b69e054c473b4a8b817cb52b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363342"
---
# <a name="step-2-categorize-the-adapter-and-connection-properties"></a><span data-ttu-id="535d0-102">第 2 步：适配器和连接属性进行分类</span><span class="sxs-lookup"><span data-stu-id="535d0-102">Step 2: Categorize the Adapter and Connection Properties</span></span>
<span data-ttu-id="535d0-103">![步骤 2 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span><span class="sxs-lookup"><span data-stu-id="535d0-103">![Step 2 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span></span>  
  
 <span data-ttu-id="535d0-104">**若要完成的时间：** 30 分钟</span><span class="sxs-lookup"><span data-stu-id="535d0-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="535d0-105">在此步骤中，你将更新**EchoAdapterBindingElement**并**EchoAdapterBindingElementExtensionElement**类，以向您的适配器和连接属性分配一个类别。</span><span class="sxs-lookup"><span data-stu-id="535d0-105">In this step, you update the **EchoAdapterBindingElement** and **EchoAdapterBindingElementExtensionElement** classes to assign a category to your adapter and connection properties.</span></span> <span data-ttu-id="535d0-106">通过这样做，属性以逻辑方式按类别分组中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]工具。</span><span class="sxs-lookup"><span data-stu-id="535d0-106">By doing so, properties are logically grouped by category in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools.</span></span> <span data-ttu-id="535d0-107">例如，如果你想**应用程序**， **EnableAuthentication**，并**主机名**属性，以显示下**连接**类别，如下所示，您需要将连接类别分配给每个应用程序、 EnableAuthentication 和主机名的属性。</span><span class="sxs-lookup"><span data-stu-id="535d0-107">For example, if you want the **Application**, **EnableAuthentication**, and **Hostname** properties to appear under the **Connection** category as shown below, you need to assign the Connection category to each of the Application, EnableAuthentication, and Hostname properties.</span></span>  
  
 <span data-ttu-id="535d0-108">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c7c0c013-6651-4c32-9f8b-b546a68a0267.gif "c7c0c013-6651-4c32-9f8b-b546a68a0267")</span><span class="sxs-lookup"><span data-stu-id="535d0-108">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c7c0c013-6651-4c32-9f8b-b546a68a0267.gif "c7c0c013-6651-4c32-9f8b-b546a68a0267")</span></span>  
  
 <span data-ttu-id="535d0-109">同样，如果你想**InboundFileFilter**并**InboundFleSystemWatcherFolder**属性，以显示下**入站**类别，如下所示，你需要将入站的类别分配给每个。</span><span class="sxs-lookup"><span data-stu-id="535d0-109">Similarly, if you want the **InboundFileFilter** and **InboundFleSystemWatcherFolder** properties to appear under the **Inbound** category as shown below, you need to assign the Inbound category to each.</span></span> <span data-ttu-id="535d0-110">如果你想**计数**并**EnableConnectionPooling**显示下方**杂项**类别中，您需要为每个分配的杂项类别。</span><span class="sxs-lookup"><span data-stu-id="535d0-110">If you want **Count** and **EnableConnectionPooling** to appear under the **Misc** category, you need to assign the Misc category to each.</span></span>  
  
 <span data-ttu-id="535d0-111">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2acb7677-8b50-4e45-96a3-42d0e2011f19.gif "2acb7677-8b50-4e45-96a3-42d0e2011f19")</span><span class="sxs-lookup"><span data-stu-id="535d0-111">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2acb7677-8b50-4e45-96a3-42d0e2011f19.gif "2acb7677-8b50-4e45-96a3-42d0e2011f19")</span></span>  
  
 <span data-ttu-id="535d0-112">请记住，您可以分配你选择的任何类别名称的属性。</span><span class="sxs-lookup"><span data-stu-id="535d0-112">Keep in mind that you can assign a property with any category name you choose.</span></span> <span data-ttu-id="535d0-113">在此示例中，由于 EnableConnnectionPooling 属性不属于任何其他类别，因此我们归类为杂项 （其他）。</span><span class="sxs-lookup"><span data-stu-id="535d0-113">In this example, since the EnableConnnectionPooling property does not belong to any other categories, we categorize it as Misc (Miscellaneous).</span></span> <span data-ttu-id="535d0-114">关于 InboundFileFilter 属性，因为在此示例中，在入站处理期间使用它就更适合要分配给属性，而不是其他入站。</span><span class="sxs-lookup"><span data-stu-id="535d0-114">As to the InboundFileFilter property, since it is used during the inbound handling within the example, it is more appropriate to assign Inbound to the property, rather than Miscellaneous.</span></span> <span data-ttu-id="535d0-115">下面是 echo 适配器的完成自定义属性分类。</span><span class="sxs-lookup"><span data-stu-id="535d0-115">Here is the complete custom property categorization for the echo adapter.</span></span>  
  
|<span data-ttu-id="535d0-116">**属性**</span><span class="sxs-lookup"><span data-stu-id="535d0-116">**Property**</span></span>|<span data-ttu-id="535d0-117">**类别**</span><span class="sxs-lookup"><span data-stu-id="535d0-117">**Category**</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="535d0-118">InboundFileFilter</span><span class="sxs-lookup"><span data-stu-id="535d0-118">InboundFileFilter</span></span>|<span data-ttu-id="535d0-119">入站</span><span class="sxs-lookup"><span data-stu-id="535d0-119">Inbound</span></span>|  
|<span data-ttu-id="535d0-120">InboundFileSystemWatcherFolder</span><span class="sxs-lookup"><span data-stu-id="535d0-120">InboundFileSystemWatcherFolder</span></span>|<span data-ttu-id="535d0-121">入站</span><span class="sxs-lookup"><span data-stu-id="535d0-121">Inbound</span></span>|  
|<span data-ttu-id="535d0-122">Count</span><span class="sxs-lookup"><span data-stu-id="535d0-122">Count</span></span>|<span data-ttu-id="535d0-123">杂项</span><span class="sxs-lookup"><span data-stu-id="535d0-123">Misc</span></span>|  
|<span data-ttu-id="535d0-124">EnableConnectionPooling</span><span class="sxs-lookup"><span data-stu-id="535d0-124">EnableConnectionPooling</span></span>|<span data-ttu-id="535d0-125">杂项</span><span class="sxs-lookup"><span data-stu-id="535d0-125">Misc</span></span>|  
|<span data-ttu-id="535d0-126">应用程序</span><span class="sxs-lookup"><span data-stu-id="535d0-126">Application</span></span>|<span data-ttu-id="535d0-127">连接</span><span class="sxs-lookup"><span data-stu-id="535d0-127">Connection</span></span>|  
|<span data-ttu-id="535d0-128">EnableAuthentication</span><span class="sxs-lookup"><span data-stu-id="535d0-128">EnableAuthentication</span></span>|<span data-ttu-id="535d0-129">连接</span><span class="sxs-lookup"><span data-stu-id="535d0-129">Connection</span></span>|  
|<span data-ttu-id="535d0-130">Hostname</span><span class="sxs-lookup"><span data-stu-id="535d0-130">Hostname</span></span>|<span data-ttu-id="535d0-131">连接</span><span class="sxs-lookup"><span data-stu-id="535d0-131">Connection</span></span>|  
|<span data-ttu-id="535d0-132">EchoInUpperCase</span><span class="sxs-lookup"><span data-stu-id="535d0-132">EchoInUpperCase</span></span>|<span data-ttu-id="535d0-133">格式</span><span class="sxs-lookup"><span data-stu-id="535d0-133">Format</span></span>|  
  
 <span data-ttu-id="535d0-134">除了这些更改，还修改的 Dispose 方法**EchoAdapterHandlerBase**。</span><span class="sxs-lookup"><span data-stu-id="535d0-134">In addition to those changes, you also modify the Dispose method of **EchoAdapterHandlerBase**.</span></span>  
  
 <span data-ttu-id="535d0-135">有关公开 echo 适配器的适配器属性，请参阅适配器属性部分的[教程 1:开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="535d0-135">For the adapter properties exposed by the echo adapter, see the adapter properties section of the [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="535d0-136">先决条件</span><span class="sxs-lookup"><span data-stu-id="535d0-136">Prerequisites</span></span>  
 <span data-ttu-id="535d0-137">在开始此步骤之前，必须完成[步骤 1:使用 WCF LOB 适配器开发向导创建 Echo 适配器项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="535d0-137">Before you begin this step, you must complete [Step 1: Use the WCF LOB Adapter Development Wizard to Create the Echo Adapter Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md).</span></span> <span data-ttu-id="535d0-138">您还应熟悉`System.ServiceModel.Configuration.BindingElementExtensionElement`和`System.ServiceModel.Configuration.StandardBindingElement`类。</span><span class="sxs-lookup"><span data-stu-id="535d0-138">You should also be familiar with the `System.ServiceModel.Configuration.BindingElementExtensionElement` and `System.ServiceModel.Configuration.StandardBindingElement` classes.</span></span>  
  
## <a name="update-the-echoadapterhandlerbase-dispose-method"></a><span data-ttu-id="535d0-139">更新 EchoAdapterHandlerBase Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="535d0-139">Update the EchoAdapterHandlerBase Dispose method</span></span>  
  
1.  <span data-ttu-id="535d0-140">在中**解决方案资源管理器**，双击**EchoAdapterHandlerBase.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="535d0-140">In **Solution Explorer**, double-click the **EchoAdapterHandlerBase.cs** file.</span></span>  
  
2.  <span data-ttu-id="535d0-141">删除以下语句从**Dispose**方法：</span><span class="sxs-lookup"><span data-stu-id="535d0-141">Remove the following statement from the **Dispose** method:</span></span>  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     <span data-ttu-id="535d0-142">修改后的方法应类似于下面所示：</span><span class="sxs-lookup"><span data-stu-id="535d0-142">The revised method should look similar to the following:</span></span>  
  
    ```csharp  
    protected virtual void Dispose(bool disposing)  
    {  
       //  
       //TODO: Implement Dispose. Override this method in respective Handler classes  
       //  
    }  
    ```  
  
## <a name="update-the-adapter-properties-class"></a><span data-ttu-id="535d0-143">更新适配器属性类</span><span class="sxs-lookup"><span data-stu-id="535d0-143">Update the Adapter properties class</span></span>  
  
1.  <span data-ttu-id="535d0-144">在中**解决方案资源管理器**，双击**EchoAdapterBindingElement.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="535d0-144">In **Solution Explorer**, double-click the **EchoAdapterBindingElement.cs** file.</span></span>  
  
2.  <span data-ttu-id="535d0-145">在 Visual Studio 编辑器中，展开**自定义生成的属性**区域。</span><span class="sxs-lookup"><span data-stu-id="535d0-145">In the Visual Studio editor, expand the **Custom Generated Properties** region.</span></span>  
  
3.  <span data-ttu-id="535d0-146">若要将分配**杂项**到类别**计数**属性的开头添加下面的单个语句**计数**实现。</span><span class="sxs-lookup"><span data-stu-id="535d0-146">To assign the **Misc** category to the **Count** property, add the following single statement to the beginning of the **Count** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
     <span data-ttu-id="535d0-147">**计数**实现现在应匹配以下内容：</span><span class="sxs-lookup"><span data-stu-id="535d0-147">The **Count** implementation should now match the following:</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="535d0-148">若要将分配**杂项**到类别**EnableConnectionPooling**属性的开头添加下面的单个语句**EnableConnectionPooling**实现。</span><span class="sxs-lookup"><span data-stu-id="535d0-148">To assign the **Misc** category to the **EnableConnectionPooling** property, add the following single statement to the beginning of the **EnableConnectionPooling** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
5.  <span data-ttu-id="535d0-149">若要将分配**入站**到类别**InboundFileFilter**属性的开头添加下面的单个语句**InboundFileFilter**实现。</span><span class="sxs-lookup"><span data-stu-id="535d0-149">To assign the **Inbound** category to the **InboundFileFilter** property, add the following single statement to the beginning of the **InboundFileFilter** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
6.  <span data-ttu-id="535d0-150">若要将分配**入站**categoryto **inboundFleSystemWatcherFolder**属性的开头添加下面的单个语句**inboundFleSystemWatcherFolder**实现。</span><span class="sxs-lookup"><span data-stu-id="535d0-150">To assign the **Inbound** categoryto **inboundFleSystemWatcherFolder** property, add the following single statement to the beginning of the **inboundFleSystemWatcherFolder** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
7.  <span data-ttu-id="535d0-151">检查以确保中的代码**自定义生成的属性**区域匹配以下：</span><span class="sxs-lookup"><span data-stu-id="535d0-151">Check to ensure that the code in the **Custom Generated Properties** region matches the following:</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("enableConnectionPooling", DefaultValue = true)]  
    public bool EnableConnectionPooling  
    {  
        get  
        {  
            return ((bool)(base["EnableConnectionPooling"]));  
        }  
        set  
        {  
            base["EnableConnectionPooling"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileFilter", DefaultValue = "*.txt")]  
    public string InboundFileFilter  
    {  
        get  
        {  
            return ((string)(base["InboundFileFilter"]));  
        }  
        set  
        {  
            base["InboundFileFilter"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileSystemWatcherFolder", DefaultValue = "{InboundFileSystemWatcherFolder}")]  
    public string InboundFileSystemWatcherFolder  
    {  
        get  
        {  
            return ((string)(base["InboundFileSystemWatcherFolder"]));  
        }  
        set  
        {  
            base["InboundFileSystemWatcherFolder"] = value;  
        }  
    }  
  
    #endregion Custom Generated Properties  
    ```  
  
## <a name="update-the-connection-properties"></a><span data-ttu-id="535d0-152">更新连接属性</span><span class="sxs-lookup"><span data-stu-id="535d0-152">Update the Connection Properties</span></span>  
  
1.  <span data-ttu-id="535d0-153">在中**解决方案资源管理器**，双击**EchoAdapterConnectionUri.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="535d0-153">In **Solution Explorer**, double-click the **EchoAdapterConnectionUri.cs** file.</span></span>  
  
2.  <span data-ttu-id="535d0-154">在 Visual Studio 编辑器中，展开**自定义生成的属性**区域。</span><span class="sxs-lookup"><span data-stu-id="535d0-154">In the Visual Studio editor, expand the **Custom Generated Properties** region.</span></span>  
  
3.  <span data-ttu-id="535d0-155">若要将分配**格式**到类别**EchoInUpperCase**属性的开头添加下面的单个语句**EchoInUpperCase**实现。</span><span class="sxs-lookup"><span data-stu-id="535d0-155">To assign the **Format** category to the **EchoInUpperCase** property, add the following single statement to the beginning of the **EchoInUpperCase** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Format")]  
    ```  
  
4.  <span data-ttu-id="535d0-156">若要将分配**连接**到类别**主机名**属性的开头添加下面的单个语句**主机名**实现。</span><span class="sxs-lookup"><span data-stu-id="535d0-156">To assign the **Connection** category to the **Hostname** property, add the following single statement to the beginning of the **Hostname** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
5.  <span data-ttu-id="535d0-157">若要将分配**连接**到类别**应用程序**属性的开头添加下面的单个语句**应用程序**实现。</span><span class="sxs-lookup"><span data-stu-id="535d0-157">To assign the **Connection** category to the **Application** property, add the following single statement to the beginning of the **Application** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
6.  <span data-ttu-id="535d0-158">若要将分配**连接**categoryto **EnableAuthentication**属性的开头添加下面的单个语句**EnableAuthentication**实现。</span><span class="sxs-lookup"><span data-stu-id="535d0-158">To assign the **Connection** categoryto **EnableAuthentication** property, add the following single statement to the beginning of the **EnableAuthentication** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
7.  <span data-ttu-id="535d0-159">检查以确保中的代码**自定义生成的属性**区域匹配以下：</span><span class="sxs-lookup"><span data-stu-id="535d0-159">Check to ensure that the code in the **Custom Generated Properties** region matches the following:</span></span>  
  
    ```csharp  
    #region Custom Generated Properties  
            [System.ComponentModel.Category("Format")]  
            public bool EchoInUpperCase  
            {  
                get  
                {  
                    return this.echoInUpperCase;  
                }  
                set  
                {  
                    this.echoInUpperCase = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Hostname  
            {  
                get  
                {  
                    return this.hostname;  
                }  
                set  
                {  
                    this.hostname = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Application  
            {  
                get  
                {  
                    return this.application;  
                }  
                set  
                {  
                    this.application = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public bool EnableAuthentication  
            {  
                get  
                {  
                    return this.enableAuthentication;  
                }  
                set  
                {  
                    this.enableAuthentication = value;  
                }  
            }  
            #endregion Custom Generated Properties  
    ```  
  
8.  <span data-ttu-id="535d0-160">在 Visual Studio 中，从**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="535d0-160">In Visual Studio, from the **File** menu, click **Save All**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="535d0-161">保存所做的工作。</span><span class="sxs-lookup"><span data-stu-id="535d0-161">You saved your work.</span></span> <span data-ttu-id="535d0-162">可以安全地关闭 Visual Studio 或转到下一步，[步骤 3:实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="535d0-162">You can safely close Visual Studio at this time or go to the next step, [Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="535d0-163">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="535d0-163">What Did I Just Do?</span></span>  
 <span data-ttu-id="535d0-164">你刚刚更新了类，以向公开 echo 适配器的每个适配器和连接属性分配一个类别。</span><span class="sxs-lookup"><span data-stu-id="535d0-164">You just updated classes to assign a category to each adapter and connection property exposed by the echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="535d0-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="535d0-165">Next Steps</span></span>  
 <span data-ttu-id="535d0-166">您实现连接、 元数据浏览、 搜索和解析功能和出站消息交换。</span><span class="sxs-lookup"><span data-stu-id="535d0-166">You implement connection, metadata browsing, searching, and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="535d0-167">最后，您生成并部署 echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="535d0-167">Lastly, you build and deploy the echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535d0-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="535d0-168">See Also</span></span>  
 <span data-ttu-id="535d0-169">[步骤 3：实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="535d0-169">[Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="535d0-170">教程 1:开发 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="535d0-170">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)