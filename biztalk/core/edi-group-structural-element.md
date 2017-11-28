---
title: "EDI 组结构化元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 100a7118-9c02-474e-8685-9e4bb6f52e81
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 555d7b86e069adda4f7761b698793fd4ec2af721
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-group-structural-element"></a><span data-ttu-id="176df-102">EDI 组结构元素</span><span class="sxs-lookup"><span data-stu-id="176df-102">EDI Group Structural Element</span></span>
<span data-ttu-id="176df-103">组包含一个或多个事务集。</span><span class="sxs-lookup"><span data-stu-id="176df-103">The group contains one or more transaction sets.</span></span> <span data-ttu-id="176df-104">一个 EDIFACT 组必须包含同一类型的事务集。</span><span class="sxs-lookup"><span data-stu-id="176df-104">An EDIFACT group must contain transaction sets of the same type.</span></span> <span data-ttu-id="176df-105">一个 X12 组可能包含类似类型的事务集（基于事务集 - 组 (GS01-ST01) 映射）或相同类型的事务集。</span><span class="sxs-lookup"><span data-stu-id="176df-105">An X12 group may contain transaction sets of similar type (based on the transaction set – group (GS01-ST01) mapping) or transaction sets of the same type.</span></span> <span data-ttu-id="176df-106">列表类似 X12 事务集 (ST01)，可以在一个组 (GS01) 一起发生这种情况下表。</span><span class="sxs-lookup"><span data-stu-id="176df-106">The table below lists similar X12 transaction sets (ST01), which can occur together in a single group (GS01).</span></span>  
  
|<span data-ttu-id="176df-107">GS01</span><span class="sxs-lookup"><span data-stu-id="176df-107">GS01</span></span>|<span data-ttu-id="176df-108">ST01</span><span class="sxs-lookup"><span data-stu-id="176df-108">ST01</span></span>|  
|----------|----------|  
|<span data-ttu-id="176df-109">CF</span><span class="sxs-lookup"><span data-stu-id="176df-109">CF</span></span>|<span data-ttu-id="176df-110">844</span><span class="sxs-lookup"><span data-stu-id="176df-110">844</span></span>|  
|<span data-ttu-id="176df-111">CF</span><span class="sxs-lookup"><span data-stu-id="176df-111">CF</span></span>|<span data-ttu-id="176df-112">849</span><span class="sxs-lookup"><span data-stu-id="176df-112">849</span></span>|  
|<span data-ttu-id="176df-113">DX</span><span class="sxs-lookup"><span data-stu-id="176df-113">DX</span></span>|<span data-ttu-id="176df-114">894</span><span class="sxs-lookup"><span data-stu-id="176df-114">894</span></span>|  
|<span data-ttu-id="176df-115">DX</span><span class="sxs-lookup"><span data-stu-id="176df-115">DX</span></span>|<span data-ttu-id="176df-116">895</span><span class="sxs-lookup"><span data-stu-id="176df-116">895</span></span>|  
|<span data-ttu-id="176df-117">FR</span><span class="sxs-lookup"><span data-stu-id="176df-117">FR</span></span>|<span data-ttu-id="176df-118">821</span><span class="sxs-lookup"><span data-stu-id="176df-118">821</span></span>|  
|<span data-ttu-id="176df-119">FR</span><span class="sxs-lookup"><span data-stu-id="176df-119">FR</span></span>|<span data-ttu-id="176df-120">827</span><span class="sxs-lookup"><span data-stu-id="176df-120">827</span></span>|  
|<span data-ttu-id="176df-121">GC</span><span class="sxs-lookup"><span data-stu-id="176df-121">GC</span></span>|<span data-ttu-id="176df-122">920</span><span class="sxs-lookup"><span data-stu-id="176df-122">920</span></span>|  
|<span data-ttu-id="176df-123">GC</span><span class="sxs-lookup"><span data-stu-id="176df-123">GC</span></span>|<span data-ttu-id="176df-124">924</span><span class="sxs-lookup"><span data-stu-id="176df-124">924</span></span>|  
|<span data-ttu-id="176df-125">GC</span><span class="sxs-lookup"><span data-stu-id="176df-125">GC</span></span>|<span data-ttu-id="176df-126">925</span><span class="sxs-lookup"><span data-stu-id="176df-126">925</span></span>|  
|<span data-ttu-id="176df-127">GC</span><span class="sxs-lookup"><span data-stu-id="176df-127">GC</span></span>|<span data-ttu-id="176df-128">926</span><span class="sxs-lookup"><span data-stu-id="176df-128">926</span></span>|  
|<span data-ttu-id="176df-129">HC</span><span class="sxs-lookup"><span data-stu-id="176df-129">HC</span></span>|<span data-ttu-id="176df-130">837</span><span class="sxs-lookup"><span data-stu-id="176df-130">837</span></span>|  
|<span data-ttu-id="176df-131">HC</span><span class="sxs-lookup"><span data-stu-id="176df-131">HC</span></span>|<span data-ttu-id="176df-132">837_D</span><span class="sxs-lookup"><span data-stu-id="176df-132">837_D</span></span>|  
|<span data-ttu-id="176df-133">HC</span><span class="sxs-lookup"><span data-stu-id="176df-133">HC</span></span>|<span data-ttu-id="176df-134">837_I</span><span class="sxs-lookup"><span data-stu-id="176df-134">837_I</span></span>|  
|<span data-ttu-id="176df-135">HC</span><span class="sxs-lookup"><span data-stu-id="176df-135">HC</span></span>|<span data-ttu-id="176df-136">837_P</span><span class="sxs-lookup"><span data-stu-id="176df-136">837_P</span></span>|  
|<span data-ttu-id="176df-137">IA</span><span class="sxs-lookup"><span data-stu-id="176df-137">IA</span></span>|<span data-ttu-id="176df-138">110</span><span class="sxs-lookup"><span data-stu-id="176df-138">110</span></span>|  
|<span data-ttu-id="176df-139">IA</span><span class="sxs-lookup"><span data-stu-id="176df-139">IA</span></span>|<span data-ttu-id="176df-140">980</span><span class="sxs-lookup"><span data-stu-id="176df-140">980</span></span>|  
|<span data-ttu-id="176df-141">IO</span><span class="sxs-lookup"><span data-stu-id="176df-141">IO</span></span>|<span data-ttu-id="176df-142">310</span><span class="sxs-lookup"><span data-stu-id="176df-142">310</span></span>|  
|<span data-ttu-id="176df-143">IO</span><span class="sxs-lookup"><span data-stu-id="176df-143">IO</span></span>|<span data-ttu-id="176df-144">312</span><span class="sxs-lookup"><span data-stu-id="176df-144">312</span></span>|  
|<span data-ttu-id="176df-145">ME</span><span class="sxs-lookup"><span data-stu-id="176df-145">ME</span></span>|<span data-ttu-id="176df-146">198</span><span class="sxs-lookup"><span data-stu-id="176df-146">198</span></span>|  
|<span data-ttu-id="176df-147">ME</span><span class="sxs-lookup"><span data-stu-id="176df-147">ME</span></span>|<span data-ttu-id="176df-148">200</span><span class="sxs-lookup"><span data-stu-id="176df-148">200</span></span>|  
|<span data-ttu-id="176df-149">ME</span><span class="sxs-lookup"><span data-stu-id="176df-149">ME</span></span>|<span data-ttu-id="176df-150">201</span><span class="sxs-lookup"><span data-stu-id="176df-150">201</span></span>|  
|<span data-ttu-id="176df-151">ME</span><span class="sxs-lookup"><span data-stu-id="176df-151">ME</span></span>|<span data-ttu-id="176df-152">245</span><span class="sxs-lookup"><span data-stu-id="176df-152">245</span></span>|  
|<span data-ttu-id="176df-153">ME</span><span class="sxs-lookup"><span data-stu-id="176df-153">ME</span></span>|<span data-ttu-id="176df-154">261</span><span class="sxs-lookup"><span data-stu-id="176df-154">261</span></span>|  
|<span data-ttu-id="176df-155">ME</span><span class="sxs-lookup"><span data-stu-id="176df-155">ME</span></span>|<span data-ttu-id="176df-156">262</span><span class="sxs-lookup"><span data-stu-id="176df-156">262</span></span>|  
|<span data-ttu-id="176df-157">ME</span><span class="sxs-lookup"><span data-stu-id="176df-157">ME</span></span>|<span data-ttu-id="176df-158">263</span><span class="sxs-lookup"><span data-stu-id="176df-158">263</span></span>|  
|<span data-ttu-id="176df-159">ME</span><span class="sxs-lookup"><span data-stu-id="176df-159">ME</span></span>|<span data-ttu-id="176df-160">833</span><span class="sxs-lookup"><span data-stu-id="176df-160">833</span></span>|  
|<span data-ttu-id="176df-161">ME</span><span class="sxs-lookup"><span data-stu-id="176df-161">ME</span></span>|<span data-ttu-id="176df-162">872</span><span class="sxs-lookup"><span data-stu-id="176df-162">872</span></span>|  
|<span data-ttu-id="176df-163">MG</span><span class="sxs-lookup"><span data-stu-id="176df-163">MG</span></span>|<span data-ttu-id="176df-164">203</span><span class="sxs-lookup"><span data-stu-id="176df-164">203</span></span>|  
|<span data-ttu-id="176df-165">MG</span><span class="sxs-lookup"><span data-stu-id="176df-165">MG</span></span>|<span data-ttu-id="176df-166">206</span><span class="sxs-lookup"><span data-stu-id="176df-166">206</span></span>|  
|<span data-ttu-id="176df-167">MG</span><span class="sxs-lookup"><span data-stu-id="176df-167">MG</span></span>|<span data-ttu-id="176df-168">259</span><span class="sxs-lookup"><span data-stu-id="176df-168">259</span></span>|  
|<span data-ttu-id="176df-169">MG</span><span class="sxs-lookup"><span data-stu-id="176df-169">MG</span></span>|<span data-ttu-id="176df-170">260</span><span class="sxs-lookup"><span data-stu-id="176df-170">260</span></span>|  
|<span data-ttu-id="176df-171">MG</span><span class="sxs-lookup"><span data-stu-id="176df-171">MG</span></span>|<span data-ttu-id="176df-172">264</span><span class="sxs-lookup"><span data-stu-id="176df-172">264</span></span>|  
|<span data-ttu-id="176df-173">MG</span><span class="sxs-lookup"><span data-stu-id="176df-173">MG</span></span>|<span data-ttu-id="176df-174">266</span><span class="sxs-lookup"><span data-stu-id="176df-174">266</span></span>|  
|<span data-ttu-id="176df-175">OG</span><span class="sxs-lookup"><span data-stu-id="176df-175">OG</span></span>|<span data-ttu-id="176df-176">875</span><span class="sxs-lookup"><span data-stu-id="176df-176">875</span></span>|  
|<span data-ttu-id="176df-177">OG</span><span class="sxs-lookup"><span data-stu-id="176df-177">OG</span></span>|<span data-ttu-id="176df-178">876</span><span class="sxs-lookup"><span data-stu-id="176df-178">876</span></span>|  
|<span data-ttu-id="176df-179">PK</span><span class="sxs-lookup"><span data-stu-id="176df-179">PK</span></span>|<span data-ttu-id="176df-180">196</span><span class="sxs-lookup"><span data-stu-id="176df-180">196</span></span>|  
|<span data-ttu-id="176df-181">PK</span><span class="sxs-lookup"><span data-stu-id="176df-181">PK</span></span>|<span data-ttu-id="176df-182">839</span><span class="sxs-lookup"><span data-stu-id="176df-182">839</span></span>|  
|<span data-ttu-id="176df-183">QG</span><span class="sxs-lookup"><span data-stu-id="176df-183">QG</span></span>|<span data-ttu-id="176df-184">878</span><span class="sxs-lookup"><span data-stu-id="176df-184">878</span></span>|  
|<span data-ttu-id="176df-185">QG</span><span class="sxs-lookup"><span data-stu-id="176df-185">QG</span></span>|<span data-ttu-id="176df-186">879</span><span class="sxs-lookup"><span data-stu-id="176df-186">879</span></span>|  
|<span data-ttu-id="176df-187">QG</span><span class="sxs-lookup"><span data-stu-id="176df-187">QG</span></span>|<span data-ttu-id="176df-188">888</span><span class="sxs-lookup"><span data-stu-id="176df-188">888</span></span>|  
|<span data-ttu-id="176df-189">QG</span><span class="sxs-lookup"><span data-stu-id="176df-189">QG</span></span>|<span data-ttu-id="176df-190">889</span><span class="sxs-lookup"><span data-stu-id="176df-190">889</span></span>|  
|<span data-ttu-id="176df-191">QG</span><span class="sxs-lookup"><span data-stu-id="176df-191">QG</span></span>|<span data-ttu-id="176df-192">896</span><span class="sxs-lookup"><span data-stu-id="176df-192">896</span></span>|  
|<span data-ttu-id="176df-193">QO</span><span class="sxs-lookup"><span data-stu-id="176df-193">QO</span></span>|<span data-ttu-id="176df-194">313</span><span class="sxs-lookup"><span data-stu-id="176df-194">313</span></span>|  
|<span data-ttu-id="176df-195">QO</span><span class="sxs-lookup"><span data-stu-id="176df-195">QO</span></span>|<span data-ttu-id="176df-196">315</span><span class="sxs-lookup"><span data-stu-id="176df-196">315</span></span>|  
|<span data-ttu-id="176df-197">RO</span><span class="sxs-lookup"><span data-stu-id="176df-197">RO</span></span>|<span data-ttu-id="176df-198">300</span><span class="sxs-lookup"><span data-stu-id="176df-198">300</span></span>|  
|<span data-ttu-id="176df-199">RO</span><span class="sxs-lookup"><span data-stu-id="176df-199">RO</span></span>|<span data-ttu-id="176df-200">301</span><span class="sxs-lookup"><span data-stu-id="176df-200">301</span></span>|  
|<span data-ttu-id="176df-201">RO</span><span class="sxs-lookup"><span data-stu-id="176df-201">RO</span></span>|<span data-ttu-id="176df-202">303</span><span class="sxs-lookup"><span data-stu-id="176df-202">303</span></span>|  
|<span data-ttu-id="176df-203">RQ</span><span class="sxs-lookup"><span data-stu-id="176df-203">RQ</span></span>|<span data-ttu-id="176df-204">836</span><span class="sxs-lookup"><span data-stu-id="176df-204">836</span></span>|  
|<span data-ttu-id="176df-205">RQ</span><span class="sxs-lookup"><span data-stu-id="176df-205">RQ</span></span>|<span data-ttu-id="176df-206">840</span><span class="sxs-lookup"><span data-stu-id="176df-206">840</span></span>|  
|<span data-ttu-id="176df-207">RS</span><span class="sxs-lookup"><span data-stu-id="176df-207">RS</span></span>|<span data-ttu-id="176df-208">869</span><span class="sxs-lookup"><span data-stu-id="176df-208">869</span></span>|  
|<span data-ttu-id="176df-209">RS</span><span class="sxs-lookup"><span data-stu-id="176df-209">RS</span></span>|<span data-ttu-id="176df-210">870</span><span class="sxs-lookup"><span data-stu-id="176df-210">870</span></span>|  
|<span data-ttu-id="176df-211">SL</span><span class="sxs-lookup"><span data-stu-id="176df-211">SL</span></span>|<span data-ttu-id="176df-212">135</span><span class="sxs-lookup"><span data-stu-id="176df-212">135</span></span>|  
|<span data-ttu-id="176df-213">SL</span><span class="sxs-lookup"><span data-stu-id="176df-213">SL</span></span>|<span data-ttu-id="176df-214">139</span><span class="sxs-lookup"><span data-stu-id="176df-214">139</span></span>|  
|<span data-ttu-id="176df-215">SO</span><span class="sxs-lookup"><span data-stu-id="176df-215">SO</span></span>|<span data-ttu-id="176df-216">302</span><span class="sxs-lookup"><span data-stu-id="176df-216">302</span></span>|  
|<span data-ttu-id="176df-217">SO</span><span class="sxs-lookup"><span data-stu-id="176df-217">SO</span></span>|<span data-ttu-id="176df-218">311</span><span class="sxs-lookup"><span data-stu-id="176df-218">311</span></span>|  
|<span data-ttu-id="176df-219">SO</span><span class="sxs-lookup"><span data-stu-id="176df-219">SO</span></span>|<span data-ttu-id="176df-220">317</span><span class="sxs-lookup"><span data-stu-id="176df-220">317</span></span>|  
|<span data-ttu-id="176df-221">SO</span><span class="sxs-lookup"><span data-stu-id="176df-221">SO</span></span>|<span data-ttu-id="176df-222">319</span><span class="sxs-lookup"><span data-stu-id="176df-222">319</span></span>|  
|<span data-ttu-id="176df-223">SO</span><span class="sxs-lookup"><span data-stu-id="176df-223">SO</span></span>|<span data-ttu-id="176df-224">322</span><span class="sxs-lookup"><span data-stu-id="176df-224">322</span></span>|  
|<span data-ttu-id="176df-225">SO</span><span class="sxs-lookup"><span data-stu-id="176df-225">SO</span></span>|<span data-ttu-id="176df-226">323</span><span class="sxs-lookup"><span data-stu-id="176df-226">323</span></span>|  
|<span data-ttu-id="176df-227">SO</span><span class="sxs-lookup"><span data-stu-id="176df-227">SO</span></span>|<span data-ttu-id="176df-228">324</span><span class="sxs-lookup"><span data-stu-id="176df-228">324</span></span>|  
|<span data-ttu-id="176df-229">SO</span><span class="sxs-lookup"><span data-stu-id="176df-229">SO</span></span>|<span data-ttu-id="176df-230">325</span><span class="sxs-lookup"><span data-stu-id="176df-230">325</span></span>|  
|<span data-ttu-id="176df-231">SO</span><span class="sxs-lookup"><span data-stu-id="176df-231">SO</span></span>|<span data-ttu-id="176df-232">326</span><span class="sxs-lookup"><span data-stu-id="176df-232">326</span></span>|  
|<span data-ttu-id="176df-233">SO</span><span class="sxs-lookup"><span data-stu-id="176df-233">SO</span></span>|<span data-ttu-id="176df-234">361</span><span class="sxs-lookup"><span data-stu-id="176df-234">361</span></span>|  
|<span data-ttu-id="176df-235">TO</span><span class="sxs-lookup"><span data-stu-id="176df-235">TO</span></span>|<span data-ttu-id="176df-236">197</span><span class="sxs-lookup"><span data-stu-id="176df-236">197</span></span>|  
|<span data-ttu-id="176df-237">TO</span><span class="sxs-lookup"><span data-stu-id="176df-237">TO</span></span>|<span data-ttu-id="176df-238">199</span><span class="sxs-lookup"><span data-stu-id="176df-238">199</span></span>|  
|<span data-ttu-id="176df-239">TO</span><span class="sxs-lookup"><span data-stu-id="176df-239">TO</span></span>|<span data-ttu-id="176df-240">265</span><span class="sxs-lookup"><span data-stu-id="176df-240">265</span></span>|  
|<span data-ttu-id="176df-241">TO</span><span class="sxs-lookup"><span data-stu-id="176df-241">TO</span></span>|<span data-ttu-id="176df-242">485</span><span class="sxs-lookup"><span data-stu-id="176df-242">485</span></span>|  
|<span data-ttu-id="176df-243">TO</span><span class="sxs-lookup"><span data-stu-id="176df-243">TO</span></span>|<span data-ttu-id="176df-244">486</span><span class="sxs-lookup"><span data-stu-id="176df-244">486</span></span>|  
|<span data-ttu-id="176df-245">TP</span><span class="sxs-lookup"><span data-stu-id="176df-245">TP</span></span>|<span data-ttu-id="176df-246">460</span><span class="sxs-lookup"><span data-stu-id="176df-246">460</span></span>|  
|<span data-ttu-id="176df-247">TP</span><span class="sxs-lookup"><span data-stu-id="176df-247">TP</span></span>|<span data-ttu-id="176df-248">463</span><span class="sxs-lookup"><span data-stu-id="176df-248">463</span></span>|  
|<span data-ttu-id="176df-249">TP</span><span class="sxs-lookup"><span data-stu-id="176df-249">TP</span></span>|<span data-ttu-id="176df-250">466</span><span class="sxs-lookup"><span data-stu-id="176df-250">466</span></span>|  
|<span data-ttu-id="176df-251">TP</span><span class="sxs-lookup"><span data-stu-id="176df-251">TP</span></span>|<span data-ttu-id="176df-252">468</span><span class="sxs-lookup"><span data-stu-id="176df-252">468</span></span>|  
|<span data-ttu-id="176df-253">TP</span><span class="sxs-lookup"><span data-stu-id="176df-253">TP</span></span>|<span data-ttu-id="176df-254">490</span><span class="sxs-lookup"><span data-stu-id="176df-254">490</span></span>|  
|<span data-ttu-id="176df-255">TP</span><span class="sxs-lookup"><span data-stu-id="176df-255">TP</span></span>|<span data-ttu-id="176df-256">492</span><span class="sxs-lookup"><span data-stu-id="176df-256">492</span></span>|  
|<span data-ttu-id="176df-257">TP</span><span class="sxs-lookup"><span data-stu-id="176df-257">TP</span></span>|<span data-ttu-id="176df-258">494</span><span class="sxs-lookup"><span data-stu-id="176df-258">494</span></span>|  
|<span data-ttu-id="176df-259">WA</span><span class="sxs-lookup"><span data-stu-id="176df-259">WA</span></span>|<span data-ttu-id="176df-260">140</span><span class="sxs-lookup"><span data-stu-id="176df-260">140</span></span>|  
|<span data-ttu-id="176df-261">WA</span><span class="sxs-lookup"><span data-stu-id="176df-261">WA</span></span>|<span data-ttu-id="176df-262">141</span><span class="sxs-lookup"><span data-stu-id="176df-262">141</span></span>|  
|<span data-ttu-id="176df-263">WA</span><span class="sxs-lookup"><span data-stu-id="176df-263">WA</span></span>|<span data-ttu-id="176df-264">142</span><span class="sxs-lookup"><span data-stu-id="176df-264">142</span></span>|  
|<span data-ttu-id="176df-265">WA</span><span class="sxs-lookup"><span data-stu-id="176df-265">WA</span></span>|<span data-ttu-id="176df-266">143</span><span class="sxs-lookup"><span data-stu-id="176df-266">143</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="176df-267">HIPAA 5010 组还允许单一组内存在不同版本的事务集。</span><span class="sxs-lookup"><span data-stu-id="176df-267">A HIPAA 5010 group also allows transaction sets of different versions within a single group.</span></span>  
  
 <span data-ttu-id="176df-268">如果在处理事务集时遇到异常，将使用 EDI 参与方属性来确定是挂起整个交换还是仅挂起失败的事务集。</span><span class="sxs-lookup"><span data-stu-id="176df-268">If an exception is encountered when processing a transaction set, EDI party properties are used to determine if the entire interchange or only the failing transaction set is suspended.</span></span>  
  
 <span data-ttu-id="176df-269">一个组必须以功能组标头（X12 中的 GS 或 EDIFACT 中的 UNG），且必须以功能组尾部（X12 中的 GE 或 EDIFACT 中的 UNE）结束。</span><span class="sxs-lookup"><span data-stu-id="176df-269">A group must start with a Functional Group Header (GS in X12 or UNG in EDIFACT), and it must end with a Functional Group Trailer (GE in X12 or UNE in EDIFACT).</span></span> <span data-ttu-id="176df-270">组标头包含发送方和接收方代码、日期和时间、与标头和尾部匹配的控制编号、可能包括在功能组内的用于定义事务集的集合的组标识符以及其他信息。</span><span class="sxs-lookup"><span data-stu-id="176df-270">The Group Header contains sender and receiver codes, a date and time, a control number that matches the header and trailer, a group identifier that defines the collection of transaction sets that may be included within the functional group, and other information.</span></span> <span data-ttu-id="176df-271">组尾部具有指示组内事务集数目的元素。</span><span class="sxs-lookup"><span data-stu-id="176df-271">The Group Trailer has an element that indicates the number of transaction sets within the group.</span></span>  
  
 <span data-ttu-id="176df-272">组在 EDIFACT 交换内是可选的。</span><span class="sxs-lookup"><span data-stu-id="176df-272">A group is optional in an EDIFACT interchange.</span></span> <span data-ttu-id="176df-273">即使不存在组（不存在 UNG 段），一个 EDIFACT 交换也可包含多个事务集。</span><span class="sxs-lookup"><span data-stu-id="176df-273">An EDIFACT interchange can contain multiple transaction sets even if no group is present (the UNG segment is not present).</span></span> <span data-ttu-id="176df-274">在此情况下，所有事务集都必须具有同一类型，因为一个组中的事务集的类型必须相同。</span><span class="sxs-lookup"><span data-stu-id="176df-274">In this case, the transaction sets must all be of the same type, as transaction sets in a single group must be of the same type.</span></span> <span data-ttu-id="176df-275">例如，APERAK 和 ORDERS 事务集不能同时出现在一个组或不具有多个组的交换中。</span><span class="sxs-lookup"><span data-stu-id="176df-275">For example, APERAK and ORDERS transaction sets could not both be present in a single group or in an interchange that does not have multiple groups.</span></span>  
  
 <span data-ttu-id="176df-276">组在 X12 交换内是必需的。</span><span class="sxs-lookup"><span data-stu-id="176df-276">A group is required in an X12 interchange.</span></span>