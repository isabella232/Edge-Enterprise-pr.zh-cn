---
title: 正则表达式 2 语法
ms.author: comanea
author: dan-wesley
manager: seanlyn
ms.date: 06/09/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 正则表达式 2 语法
ms.openlocfilehash: 9654a25d2c0474601fb719b145ebb1f59241a6d9
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979288"
---
# <span data-ttu-id="7d65a-103">正则表达式 2 (re2.h) 语法</span><span class="sxs-lookup"><span data-stu-id="7d65a-103">Regular Expression 2 (re2.h) syntax</span></span>

<span data-ttu-id="7d65a-104">正则表达式是描述字符串集的表示法。</span><span class="sxs-lookup"><span data-stu-id="7d65a-104">Regular expressions are a notation for describing sets of character strings.</span></span> <span data-ttu-id="7d65a-105">如果字符串位于正则表达式所描述的集合中，通常表示正则表达式匹配该字符串。</span><span class="sxs-lookup"><span data-stu-id="7d65a-105">When a string is in the set described by a regular expression, we often say that the regular expression matches the string.</span></span>

<span data-ttu-id="7d65a-106">最简单的正则表达式是单个文本字符。</span><span class="sxs-lookup"><span data-stu-id="7d65a-106">The simplest regular expression is a single literal character.</span></span> <span data-ttu-id="7d65a-107">除了 *\*+?()|* 等元字符，字符匹配自身。</span><span class="sxs-lookup"><span data-stu-id="7d65a-107">Except for the metacharacters like *\*+?()|*, characters match themselves.</span></span> <span data-ttu-id="7d65a-108">若要匹配元字符，请使用反斜杠将其转义，如： \+ 匹配加号字符。</span><span class="sxs-lookup"><span data-stu-id="7d65a-108">To match a metacharacter, escape it with a backslash: \+ matches a literal plus character.</span></span>

<span data-ttu-id="7d65a-109">可以更改或连接两个正则表达式，形成一个新的正则表达式：如果 *e<sub>1</sub>* 匹配 _s_，*e<sub>2</sub>* 匹配 _t_，则 *e<sub>1</sub> \* | *e<sub>2</sub>* 匹配 _s_ 或 _t_，而且*e<sub>1</sub>\* *e<sub>2</sub>* 匹配 _st_。</span><span class="sxs-lookup"><span data-stu-id="7d65a-109">Two regular expressions can be altered or concatenated to form a new regular expression: if *e<sub>1</sub>* matches _s_ and *e<sub>2</sub>* matches _t_, then *e<sub>1</sub>* | *e<sub>2</sub>* matches _s_ or _t_, and *e<sub>1</sub>* *e<sub>2</sub>*  matches _st_.</span></span>

<span data-ttu-id="7d65a-110">元字符 _\*_、_+_ 和 _?_</span><span class="sxs-lookup"><span data-stu-id="7d65a-110">The metacharacters _\*_ , _+_ , and _?_</span></span> <span data-ttu-id="7d65a-111">是重复运算符： *e<sub>1</sub>* _\*_ 匹配零个或多个（可能是不同的）字符串序列，其中每个字符串匹配 *e<sub>1</sub>*；*e<sub>1</sub>* _+_ 匹配一个或多个；*e<sub>1</sub>* _?_</span><span class="sxs-lookup"><span data-stu-id="7d65a-111">are repetition operators: *e<sub>1</sub>* _\*_ matches a sequence of zero or more (possibly different) strings, each of which match *e<sub>1</sub>*; *e<sub>1</sub>* _+_ matches one or more; *e<sub>1</sub>* _?_</span></span> <span data-ttu-id="7d65a-112">匹配零个或一个。</span><span class="sxs-lookup"><span data-stu-id="7d65a-112">matches zero or one.</span></span>

<span data-ttu-id="7d65a-113">运算符的优先级从最弱到最强排序，依次是替换、连接和重复运算符。</span><span class="sxs-lookup"><span data-stu-id="7d65a-113">The operator precedence, from weakest to strongest binding, is first alternation, then concatenation, and finally the repetition operators.</span></span> <span data-ttu-id="7d65a-114">可采用显式括号强制改变运算顺序，就像在算术表达式中一样。</span><span class="sxs-lookup"><span data-stu-id="7d65a-114">Explicit parentheses can be used to force different meanings, just as in arithmetic expressions.</span></span> <span data-ttu-id="7d65a-115">示例： _ab|cd_ 等同于 _(ab)|(cd)_；_ab\*_ 等同于 _a(b\*)_ 。</span><span class="sxs-lookup"><span data-stu-id="7d65a-115">Some examples: _ab|cd_ is equivalent to _(ab)|(cd)_ ; _ab\*_ is equivalent to _a(b\*)_ .</span></span>

<span data-ttu-id="7d65a-116">目前所介绍的语法大部分为传统的 Unix _egrep_ 正则表达式语法。</span><span class="sxs-lookup"><span data-stu-id="7d65a-116">The syntax described so far is most of the traditional Unix _egrep_ regular expression syntax.</span></span> <span data-ttu-id="7d65a-117">此子集足以描述所有常规语言：笼统来讲，常规语言是一组字符串，可在单个传递文本的过程中仅使用固定数量的内存进行匹配。</span><span class="sxs-lookup"><span data-stu-id="7d65a-117">This subset suffices to describe all regular languages: loosely speaking, a regular language is a set of strings that can be matched in a single pass through the text using only a fixed amount of memory.</span></span> <span data-ttu-id="7d65a-118">较新的正则表达式功能（尤其是 Perl 和那些已复制的功能）添加了许多新的运算符和转义序列，令正则表达式更简洁，有时含义模糊，但通常功能没有增强。</span><span class="sxs-lookup"><span data-stu-id="7d65a-118">Newer regular expression facilities (notably Perl and those that have copied it) have added many new operators and escape sequences, which make the regular expressions more concise, and sometimes more cryptic, but usually not more powerful.</span></span>

<span data-ttu-id="7d65a-119">本页列出了 RE2 接受的正则表达式语法。</span><span class="sxs-lookup"><span data-stu-id="7d65a-119">This page lists the regular expression syntax accepted by RE2.</span></span>

<span data-ttu-id="7d65a-120">还列出了 PCRE、PERL 和 VIM 接受的一些语法。</span><span class="sxs-lookup"><span data-stu-id="7d65a-120">It also lists some syntax accepted by PCRE, PERL and VIM.</span></span>

## <span data-ttu-id="7d65a-121">语法表</span><span class="sxs-lookup"><span data-stu-id="7d65a-121">Syntax tables</span></span>

| <span data-ttu-id="7d65a-122">单字符表达式的类型</span><span class="sxs-lookup"><span data-stu-id="7d65a-122">Kinds of single-character expressions</span></span> | <span data-ttu-id="7d65a-123">示例</span><span class="sxs-lookup"><span data-stu-id="7d65a-123">Examples</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-124">任何字符，可能包括换行符（s = true）</span><span class="sxs-lookup"><span data-stu-id="7d65a-124">any character, possibly including newline (s=true)</span></span> | <span data-ttu-id="7d65a-125">.</span><span class="sxs-lookup"><span data-stu-id="7d65a-125">.</span></span> |
| <span data-ttu-id="7d65a-126">字符组</span><span class="sxs-lookup"><span data-stu-id="7d65a-126">character class</span></span> | <span data-ttu-id="7d65a-127">[xyz]</span><span class="sxs-lookup"><span data-stu-id="7d65a-127">[xyz]</span></span> |
| <span data-ttu-id="7d65a-128">排除型字符组</span><span class="sxs-lookup"><span data-stu-id="7d65a-128">negated character class</span></span> | <span data-ttu-id="7d65a-129">[^xyz]</span><span class="sxs-lookup"><span data-stu-id="7d65a-129">[^xyz]</span></span> |
| <span data-ttu-id="7d65a-130">Perl 字符组（[链接](#user-content-perl)）</span><span class="sxs-lookup"><span data-stu-id="7d65a-130">Perl character class ([link](#user-content-perl))</span></span> | <span data-ttu-id="7d65a-131">\d</span><span class="sxs-lookup"><span data-stu-id="7d65a-131">\d</span></span> |
| <span data-ttu-id="7d65a-132">排除型 Perl 字符组</span><span class="sxs-lookup"><span data-stu-id="7d65a-132">negated Perl character class</span></span> | <span data-ttu-id="7d65a-133">\D</span><span class="sxs-lookup"><span data-stu-id="7d65a-133">\D</span></span> |
| <span data-ttu-id="7d65a-134">ASCII 字符组（[链接](#user-content-ascii)）</span><span class="sxs-lookup"><span data-stu-id="7d65a-134">ASCII character class ([link](#user-content-ascii))</span></span> | <span data-ttu-id="7d65a-135">[[:alpha:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-135">[[:alpha:]]</span></span> |
| <span data-ttu-id="7d65a-136">排除型 ASCII 字符组</span><span class="sxs-lookup"><span data-stu-id="7d65a-136">negated ASCII character class</span></span> | <span data-ttu-id="7d65a-137">[[:^alpha:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-137">[[:^alpha:]]</span></span> |
| <span data-ttu-id="7d65a-138">Unicode 字符组（单字母名称）</span><span class="sxs-lookup"><span data-stu-id="7d65a-138">Unicode character class (one-letter name)</span></span> | <span data-ttu-id="7d65a-139">\pN</span><span class="sxs-lookup"><span data-stu-id="7d65a-139">\pN</span></span> |
| <span data-ttu-id="7d65a-140">Unicode 字符组</span><span class="sxs-lookup"><span data-stu-id="7d65a-140">Unicode character class</span></span> | <span data-ttu-id="7d65a-141">\p{Greek}</span><span class="sxs-lookup"><span data-stu-id="7d65a-141">\p{Greek}</span></span> |
| <span data-ttu-id="7d65a-142">排除型 Unicode 字符组（单字母名称）</span><span class="sxs-lookup"><span data-stu-id="7d65a-142">negated Unicode character class (one-letter name)</span></span> | <span data-ttu-id="7d65a-143">\PN</span><span class="sxs-lookup"><span data-stu-id="7d65a-143">\PN</span></span> |
| <span data-ttu-id="7d65a-144">排除型 Unicode 字符组</span><span class="sxs-lookup"><span data-stu-id="7d65a-144">negated Unicode character class</span></span> | <span data-ttu-id="7d65a-145">\P{Greek}</span><span class="sxs-lookup"><span data-stu-id="7d65a-145">\P{Greek}</span></span> |

| | <span data-ttu-id="7d65a-146">复合匹配</span><span class="sxs-lookup"><span data-stu-id="7d65a-146">Composites</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-147">xy</span><span class="sxs-lookup"><span data-stu-id="7d65a-147">xy</span></span> | <span data-ttu-id="7d65a-148">匹配 x 后接 y</span><span class="sxs-lookup"><span data-stu-id="7d65a-148">x followed by y</span></span> |
| <span data-ttu-id="7d65a-149">x\|y</span><span class="sxs-lookup"><span data-stu-id="7d65a-149">x\|y</span></span> | <span data-ttu-id="7d65a-150">匹配 x 或 y （首选 x）</span><span class="sxs-lookup"><span data-stu-id="7d65a-150">x or y (prefer x)</span></span> |

| | <span data-ttu-id="7d65a-151">重复匹配</span><span class="sxs-lookup"><span data-stu-id="7d65a-151">Repetitions</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-152">x\*</span><span class="sxs-lookup"><span data-stu-id="7d65a-152">x\*</span></span> | <span data-ttu-id="7d65a-153">匹配零个或任意个 x，首选多匹配</span><span class="sxs-lookup"><span data-stu-id="7d65a-153">zero or more x, prefer more</span></span> |
| <span data-ttu-id="7d65a-154">x+</span><span class="sxs-lookup"><span data-stu-id="7d65a-154">x+</span></span> | <span data-ttu-id="7d65a-155">匹配至少一个 x，首选多匹配</span><span class="sxs-lookup"><span data-stu-id="7d65a-155">one or more x, prefer more</span></span> |
| <span data-ttu-id="7d65a-156">x?</span><span class="sxs-lookup"><span data-stu-id="7d65a-156">x?</span></span> | <span data-ttu-id="7d65a-157">匹配零个或一个 x，首选一个</span><span class="sxs-lookup"><span data-stu-id="7d65a-157">zero or one x, prefer one</span></span> |
| <span data-ttu-id="7d65a-158">x{n,m}</span><span class="sxs-lookup"><span data-stu-id="7d65a-158">x{n,m}</span></span> | <span data-ttu-id="7d65a-159">匹配 n 或 n+1...至多 m 个 x，首选多匹配</span><span class="sxs-lookup"><span data-stu-id="7d65a-159">n or n+1 or ... or m x, prefer more</span></span> |
| <span data-ttu-id="7d65a-160">x{n,}</span><span class="sxs-lookup"><span data-stu-id="7d65a-160">x{n,}</span></span> | <span data-ttu-id="7d65a-161">匹配至少 n 个 x，首选多匹配</span><span class="sxs-lookup"><span data-stu-id="7d65a-161">n or more x, prefer more</span></span> |
| <span data-ttu-id="7d65a-162">x{n}</span><span class="sxs-lookup"><span data-stu-id="7d65a-162">x{n}</span></span> | <span data-ttu-id="7d65a-163">匹配确定的 n 个 x</span><span class="sxs-lookup"><span data-stu-id="7d65a-163">exactly n x</span></span> |
| <span data-ttu-id="7d65a-164">x\*?</span><span class="sxs-lookup"><span data-stu-id="7d65a-164">x\*?</span></span> | <span data-ttu-id="7d65a-165">匹配零个或任意个 x，首选少匹配</span><span class="sxs-lookup"><span data-stu-id="7d65a-165">zero or more x, prefer fewer</span></span> |
| <span data-ttu-id="7d65a-166">x+?</span><span class="sxs-lookup"><span data-stu-id="7d65a-166">x+?</span></span> | <span data-ttu-id="7d65a-167">匹配至少一个 x，首选少匹配</span><span class="sxs-lookup"><span data-stu-id="7d65a-167">one or more x, prefer fewer</span></span> |
| <span data-ttu-id="7d65a-168">x??</span><span class="sxs-lookup"><span data-stu-id="7d65a-168">x??</span></span> | <span data-ttu-id="7d65a-169">匹配零个或一个 x，首选零个</span><span class="sxs-lookup"><span data-stu-id="7d65a-169">zero or one x, prefer zero</span></span> |
| <span data-ttu-id="7d65a-170">x{n,m}?</span><span class="sxs-lookup"><span data-stu-id="7d65a-170">x{n,m}?</span></span> | <span data-ttu-id="7d65a-171">匹配 n 或 n+1...至多m 个 x，首选少匹配</span><span class="sxs-lookup"><span data-stu-id="7d65a-171">n or n+1 or ... or m x, prefer fewer</span></span> |
| <span data-ttu-id="7d65a-172">x{n,}?</span><span class="sxs-lookup"><span data-stu-id="7d65a-172">x{n,}?</span></span> | <span data-ttu-id="7d65a-173">匹配至少 n 个 x，首选少匹配</span><span class="sxs-lookup"><span data-stu-id="7d65a-173">n or more x, prefer fewer</span></span> |
| <span data-ttu-id="7d65a-174">x{n}?</span><span class="sxs-lookup"><span data-stu-id="7d65a-174">x{n}?</span></span> | <span data-ttu-id="7d65a-175">匹配确定的 n 个 x</span><span class="sxs-lookup"><span data-stu-id="7d65a-175">exactly n x</span></span> |
| <span data-ttu-id="7d65a-176">x{}</span><span class="sxs-lookup"><span data-stu-id="7d65a-176">x{}</span></span> | <span data-ttu-id="7d65a-177">（等价于 x\*）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-177">(≡ x\*) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-178">x{-}</span><span class="sxs-lookup"><span data-stu-id="7d65a-178">x{-}</span></span> | <span data-ttu-id="7d65a-179">（等价于 x\*?）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-179">(≡ x\*?) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-180">x{-n}</span><span class="sxs-lookup"><span data-stu-id="7d65a-180">x{-n}</span></span> | <span data-ttu-id="7d65a-181">（等价于 x{n}?）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-181">(≡ x{n}?) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-182">x=</span><span class="sxs-lookup"><span data-stu-id="7d65a-182">x=</span></span> | <span data-ttu-id="7d65a-183">（等价于 x?）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-183">(≡ x?) (NOT SUPPORTED) VIM</span></span> |

<span data-ttu-id="7d65a-184">启动限制：计数形式 x{n,m}、x{n,} 和 x{n} 最小或最大重复个数不能超过 1000。</span><span class="sxs-lookup"><span data-stu-id="7d65a-184">Implementation restriction: The counting forms x{n,m}, x{n,}, and x{n} reject forms that create a minimum or maximum repetition count above 1000.</span></span> <span data-ttu-id="7d65a-185">无限制的重复不受此限制约束。</span><span class="sxs-lookup"><span data-stu-id="7d65a-185">Unlimited repetitions are not subject to this restriction.</span></span>

| | <span data-ttu-id="7d65a-186">所有格重复</span><span class="sxs-lookup"><span data-stu-id="7d65a-186">Possessive repetitions</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-187">x\*+</span><span class="sxs-lookup"><span data-stu-id="7d65a-187">x\*+</span></span> | <span data-ttu-id="7d65a-188">匹配零个或任意个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-188">zero or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-189">x++</span><span class="sxs-lookup"><span data-stu-id="7d65a-189">x++</span></span> | <span data-ttu-id="7d65a-190">匹配至少一个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-190">one or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-191">x?+</span><span class="sxs-lookup"><span data-stu-id="7d65a-191">x?+</span></span> | <span data-ttu-id="7d65a-192">匹配零个或一个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-192">zero or one x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-193">x {n，m} +</span><span class="sxs-lookup"><span data-stu-id="7d65a-193">x{n,m}+</span></span> | <span data-ttu-id="7d65a-194">匹配 n...或 m 个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-194">n or ... or m x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-195">x{n,}+</span><span class="sxs-lookup"><span data-stu-id="7d65a-195">x{n,}+</span></span> | <span data-ttu-id="7d65a-196">匹配至少 n 个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-196">n or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-197">x{n}+</span><span class="sxs-lookup"><span data-stu-id="7d65a-197">x{n}+</span></span> | <span data-ttu-id="7d65a-198">匹配确定的 n 个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-198">exactly n x, possessive (NOT SUPPORTED)</span></span> |

| | <span data-ttu-id="7d65a-199">分组</span><span class="sxs-lookup"><span data-stu-id="7d65a-199">Grouping</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-200">(re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-200">(re)</span></span> | <span data-ttu-id="7d65a-201">编号捕获组（子匹配）</span><span class="sxs-lookup"><span data-stu-id="7d65a-201">numbered capturing group (submatch)</span></span> |
| <span data-ttu-id="7d65a-202">(?P&lt;name&gt;re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-202">(?P&lt;name&gt;re)</span></span> | <span data-ttu-id="7d65a-203">命名 &amp; 编号捕获组（子匹配）</span><span class="sxs-lookup"><span data-stu-id="7d65a-203">named &amp; numbered capturing group (submatch)</span></span> |
| <span data-ttu-id="7d65a-204">(?&lt;name&gt;re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-204">(?&lt;name&gt;re)</span></span> | <span data-ttu-id="7d65a-205">命名 &amp; 编号捕获组（子匹配）（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-205">named &amp; numbered capturing group (submatch) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-206">(?&#39;name&#39;re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-206">(?&#39;name&#39;re)</span></span> | <span data-ttu-id="7d65a-207">命名 &amp; 编号捕获组（子匹配）（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-207">named &amp; numbered capturing group (submatch) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-208">(?:re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-208">(?:re)</span></span> | <span data-ttu-id="7d65a-209">非捕获组</span><span class="sxs-lookup"><span data-stu-id="7d65a-209">non-capturing group</span></span> |
| <span data-ttu-id="7d65a-210">(?flags)</span><span class="sxs-lookup"><span data-stu-id="7d65a-210">(?flags)</span></span> | <span data-ttu-id="7d65a-211">在当前组中设置标志；非捕获</span><span class="sxs-lookup"><span data-stu-id="7d65a-211">set flags within current group; non-capturing</span></span> |
| <span data-ttu-id="7d65a-212">(?flags:re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-212">(?flags:re)</span></span> | <span data-ttu-id="7d65a-213">在表达式中设置标志；非捕获</span><span class="sxs-lookup"><span data-stu-id="7d65a-213">set flags during re; non-capturing</span></span> |
| <span data-ttu-id="7d65a-214">(?#text)</span><span class="sxs-lookup"><span data-stu-id="7d65a-214">(?#text)</span></span> | <span data-ttu-id="7d65a-215">注释（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-215">comment (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-216">(?\|x\|y\|z)</span><span class="sxs-lookup"><span data-stu-id="7d65a-216">(?\|x\|y\|z)</span></span> | <span data-ttu-id="7d65a-217">分支编号重置（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-217">branch numbering reset (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-218">(?&gt;re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-218">(?&gt;re)</span></span> | <span data-ttu-id="7d65a-219">表达式所有格匹配 （不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-219">possessive match of re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-220">re@&gt;</span><span class="sxs-lookup"><span data-stu-id="7d65a-220">re@&gt;</span></span> | <span data-ttu-id="7d65a-221">表达式所有格匹配（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-221">possessive match of re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-222">%(re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-222">%(re)</span></span> | <span data-ttu-id="7d65a-223">非捕获组（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-223">non-capturing group (NOT SUPPORTED) VIM</span></span> |

| | <span data-ttu-id="7d65a-224">Flags</span><span class="sxs-lookup"><span data-stu-id="7d65a-224">Flags</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-225">i</span><span class="sxs-lookup"><span data-stu-id="7d65a-225">i</span></span> | <span data-ttu-id="7d65a-226">不区分大小写（默认为 false）</span><span class="sxs-lookup"><span data-stu-id="7d65a-226">case-insensitive (default false)</span></span> |
| <span data-ttu-id="7d65a-227">m</span><span class="sxs-lookup"><span data-stu-id="7d65a-227">m</span></span> | <span data-ttu-id="7d65a-228">多行模式： ^ 和 $ 匹配行首/尾，以及文本开头/结尾（默认为 false）</span><span class="sxs-lookup"><span data-stu-id="7d65a-228">multi-line mode: ^ and $ match begin/end line in addition to begin/end text (default false)</span></span> |
| <span data-ttu-id="7d65a-229">s</span><span class="sxs-lookup"><span data-stu-id="7d65a-229">s</span></span> | <span data-ttu-id="7d65a-230">let .</span><span class="sxs-lookup"><span data-stu-id="7d65a-230">let .</span></span> <span data-ttu-id="7d65a-231">匹配 \n （默认为 false）</span><span class="sxs-lookup"><span data-stu-id="7d65a-231">match \n (default false)</span></span> |
| <span data-ttu-id="7d65a-232">U</span><span class="sxs-lookup"><span data-stu-id="7d65a-232">U</span></span> | <span data-ttu-id="7d65a-233">非贪婪模式：以 x\*? 替换 x\*、x+? 替换 x+ 等（默认为 false）</span><span class="sxs-lookup"><span data-stu-id="7d65a-233">ungreedy: swap meaning of x\* and x\*?, x+ and x+?, etc (default false)</span></span> |

<span data-ttu-id="7d65a-234">标记语法为 xyz （已设置）或 -xyz （清除）或 xy-z （设置为 xy，清除 z）。</span><span class="sxs-lookup"><span data-stu-id="7d65a-234">Flag syntax is xyz (set) or -xyz (clear) or xy-z (set xy, clear z).</span></span>

|  | <span data-ttu-id="7d65a-235">空字符串</span><span class="sxs-lookup"><span data-stu-id="7d65a-235">Empty strings</span></span> |
| --- | --- |
| ^ | <span data-ttu-id="7d65a-236">文本开始或行首（m = true）</span><span class="sxs-lookup"><span data-stu-id="7d65a-236">at beginning of text or line (m=true)</span></span> |
| $ | <span data-ttu-id="7d65a-237">文本结尾（如 \z 而非 \Z）或行尾（m = true）</span><span class="sxs-lookup"><span data-stu-id="7d65a-237">at end of text (like \z not \Z) or line (m=true)</span></span> |
| <span data-ttu-id="7d65a-238">\A</span><span class="sxs-lookup"><span data-stu-id="7d65a-238">\A</span></span> | <span data-ttu-id="7d65a-239">文本开头</span><span class="sxs-lookup"><span data-stu-id="7d65a-239">at beginning of text</span></span> |
| <span data-ttu-id="7d65a-240">\b</span><span class="sxs-lookup"><span data-stu-id="7d65a-240">\b</span></span> | <span data-ttu-id="7d65a-241">匹配 ASCII 单词边界（\w 表示一端，\W、\A 或 \z 表示另一端）</span><span class="sxs-lookup"><span data-stu-id="7d65a-241">at ASCII word boundary (\w on one side and \W, \A, or \z on the other)</span></span> |
| <span data-ttu-id="7d65a-242">\B</span><span class="sxs-lookup"><span data-stu-id="7d65a-242">\B</span></span> | <span data-ttu-id="7d65a-243">匹配非 ASCII 单词边界</span><span class="sxs-lookup"><span data-stu-id="7d65a-243">not at ASCII word boundary</span></span> |
| <span data-ttu-id="7d65a-244">\g</span><span class="sxs-lookup"><span data-stu-id="7d65a-244">\g</span></span> | <span data-ttu-id="7d65a-245">匹配正在搜索的从属文本开头（不支持） PCRE</span><span class="sxs-lookup"><span data-stu-id="7d65a-245">at beginning of subtext being searched (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="7d65a-246">\G</span><span class="sxs-lookup"><span data-stu-id="7d65a-246">\G</span></span> | <span data-ttu-id="7d65a-247">匹配上一个匹配的结尾（不支持） PERL </span><span class="sxs-lookup"><span data-stu-id="7d65a-247">at end of last match (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="7d65a-248">\Z</span><span class="sxs-lookup"><span data-stu-id="7d65a-248">\Z</span></span> | <span data-ttu-id="7d65a-249">匹配必须出现在文本末尾，或在文本末尾换行前的位置（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-249">at end of text, or before newline at end of text (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-250">\z</span><span class="sxs-lookup"><span data-stu-id="7d65a-250">\z</span></span> | <span data-ttu-id="7d65a-251">匹配文本末尾</span><span class="sxs-lookup"><span data-stu-id="7d65a-251">at end of text</span></span> |
| <span data-ttu-id="7d65a-252">(?=re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-252">(?=re)</span></span> | <span data-ttu-id="7d65a-253">前向肯定界定符（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-253">before text matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-254">(?!re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-254">(?!re)</span></span> | <span data-ttu-id="7d65a-255">前向否定界定符（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-255">before text not matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-256">(?&lt;=re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-256">(?&lt;=re)</span></span> | <span data-ttu-id="7d65a-257">后向肯定界定符（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-257">after text matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-258">(?&lt;!re)</span><span class="sxs-lookup"><span data-stu-id="7d65a-258">(?&lt;!re)</span></span> | <span data-ttu-id="7d65a-259">后向否定界定符（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-259">after text not matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-260">re&amp;</span><span class="sxs-lookup"><span data-stu-id="7d65a-260">re&amp;</span></span> | <span data-ttu-id="7d65a-261">前向肯定界定符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-261">before text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-262">re@=</span><span class="sxs-lookup"><span data-stu-id="7d65a-262">re@=</span></span> | <span data-ttu-id="7d65a-263">前向肯定界定符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-263">before text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-264">re@!</span><span class="sxs-lookup"><span data-stu-id="7d65a-264">re@!</span></span> | <span data-ttu-id="7d65a-265">前向否定界定符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-265">before text not matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-266">re@&lt;=</span><span class="sxs-lookup"><span data-stu-id="7d65a-266">re@&lt;=</span></span> | <span data-ttu-id="7d65a-267">后向肯定界定符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-267">after text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-268">re@&lt;!</span><span class="sxs-lookup"><span data-stu-id="7d65a-268">re@&lt;!</span></span> | <span data-ttu-id="7d65a-269">后向否定界定符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-269">after text not matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-270">\zs</span><span class="sxs-lookup"><span data-stu-id="7d65a-270">\zs</span></span> | <span data-ttu-id="7d65a-271">设置匹配开始（同 \K）（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-271">sets start of match (= \K) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-272">\ze</span><span class="sxs-lookup"><span data-stu-id="7d65a-272">\ze</span></span> | <span data-ttu-id="7d65a-273">设置匹配结尾（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-273">sets end of match (NOT SUPPORTED) VIM</span></span> |
| \%^ | <span data-ttu-id="7d65a-274">匹配文件开头（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-274">beginning of file (NOT SUPPORTED) VIM</span></span> |
| \%$ | <span data-ttu-id="7d65a-275">匹配文件结尾（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-275">end of file (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-276">\%V</span><span class="sxs-lookup"><span data-stu-id="7d65a-276">\%V</span></span> | <span data-ttu-id="7d65a-277">在屏幕上匹配（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-277">on screen (NOT SUPPORTED) VIM</span></span> |
| \%# | <span data-ttu-id="7d65a-278">从光标位置匹配（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-278">cursor position (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-279">\%&#39;m</span><span class="sxs-lookup"><span data-stu-id="7d65a-279">\%&#39;m</span></span> | <span data-ttu-id="7d65a-280">在标记 m 的位置匹配（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-280">mark m position (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-281">\%23l</span><span class="sxs-lookup"><span data-stu-id="7d65a-281">\%23l</span></span> | <span data-ttu-id="7d65a-282">在第 23 行匹配（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-282">in line 23 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-283">\%23c</span><span class="sxs-lookup"><span data-stu-id="7d65a-283">\%23c</span></span> | <span data-ttu-id="7d65a-284">在第 23 列匹配（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-284">in column 23 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-285">\%23v</span><span class="sxs-lookup"><span data-stu-id="7d65a-285">\%23v</span></span> | <span data-ttu-id="7d65a-286">在虚拟第 23 列匹配（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-286">in virtual column 23 (NOT SUPPORTED) VIM</span></span> |

|  | <span data-ttu-id="7d65a-287">转义序列</span><span class="sxs-lookup"><span data-stu-id="7d65a-287">Escape sequences</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-288">\a</span><span class="sxs-lookup"><span data-stu-id="7d65a-288">\a</span></span> | <span data-ttu-id="7d65a-289">匹配报警符（等价于 \007）</span><span class="sxs-lookup"><span data-stu-id="7d65a-289">bell (≡ \007)</span></span> |
| <span data-ttu-id="7d65a-290">\f</span><span class="sxs-lookup"><span data-stu-id="7d65a-290">\f</span></span> | <span data-ttu-id="7d65a-291">匹配换页符（等价于 \014）</span><span class="sxs-lookup"><span data-stu-id="7d65a-291">form feed (≡ \014)</span></span> |
| <span data-ttu-id="7d65a-292">\t</span><span class="sxs-lookup"><span data-stu-id="7d65a-292">\t</span></span> | <span data-ttu-id="7d65a-293">匹配水平制表符（等价于 \011）</span><span class="sxs-lookup"><span data-stu-id="7d65a-293">horizontal tab (≡ \011)</span></span> |
| <span data-ttu-id="7d65a-294">\n</span><span class="sxs-lookup"><span data-stu-id="7d65a-294">\n</span></span> | <span data-ttu-id="7d65a-295">匹配换行符（等价于 \012）</span><span class="sxs-lookup"><span data-stu-id="7d65a-295">newline (≡ \012)</span></span> |
| <span data-ttu-id="7d65a-296">\r</span><span class="sxs-lookup"><span data-stu-id="7d65a-296">\r</span></span> | <span data-ttu-id="7d65a-297">匹配回车符（等价于 \015）</span><span class="sxs-lookup"><span data-stu-id="7d65a-297">carriage return (≡ \015)</span></span> |
| <span data-ttu-id="7d65a-298">\v</span><span class="sxs-lookup"><span data-stu-id="7d65a-298">\v</span></span> | <span data-ttu-id="7d65a-299">匹配垂直制表符（等价于 \013）</span><span class="sxs-lookup"><span data-stu-id="7d65a-299">vertical tab character (≡ \013)</span></span> |
| \* | <span data-ttu-id="7d65a-300">文本 \*，匹配任意标点字符 \*</span><span class="sxs-lookup"><span data-stu-id="7d65a-300">literal \*, for any punctuation character \*</span></span> |
| <span data-ttu-id="7d65a-301">\123</span><span class="sxs-lookup"><span data-stu-id="7d65a-301">\123</span></span> | <span data-ttu-id="7d65a-302">匹配八进制字符代码（最多三位）</span><span class="sxs-lookup"><span data-stu-id="7d65a-302">octal character code (up to three digits)</span></span> |
| <span data-ttu-id="7d65a-303">\x7F</span><span class="sxs-lookup"><span data-stu-id="7d65a-303">\x7F</span></span> | <span data-ttu-id="7d65a-304">匹配十六进制字符代码（确定两位）</span><span class="sxs-lookup"><span data-stu-id="7d65a-304">hex character code (exactly two digits)</span></span> |
| <span data-ttu-id="7d65a-305">\x{10FFFF}</span><span class="sxs-lookup"><span data-stu-id="7d65a-305">\x{10FFFF}</span></span> | <span data-ttu-id="7d65a-306">匹配十六进制字符代码</span><span class="sxs-lookup"><span data-stu-id="7d65a-306">hex character code</span></span> |
| <span data-ttu-id="7d65a-307">\C</span><span class="sxs-lookup"><span data-stu-id="7d65a-307">\C</span></span> | <span data-ttu-id="7d65a-308">匹配单字节，即使在 UTF-8 模式下</span><span class="sxs-lookup"><span data-stu-id="7d65a-308">match a single byte even in UTF-8 mode</span></span> |
| <span data-ttu-id="7d65a-309">\Q...\E</span><span class="sxs-lookup"><span data-stu-id="7d65a-309">\Q...\E</span></span> | <span data-ttu-id="7d65a-310">匹配文本 ... 即使 ... 含有标点</span><span class="sxs-lookup"><span data-stu-id="7d65a-310">literal text ... even if ... has punctuation</span></span> |
| <span data-ttu-id="7d65a-311">\1</span><span class="sxs-lookup"><span data-stu-id="7d65a-311">\1</span></span> | <span data-ttu-id="7d65a-312">匹配反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-312">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-313">\b</span><span class="sxs-lookup"><span data-stu-id="7d65a-313">\b</span></span> | <span data-ttu-id="7d65a-314">匹配退格 （不支持）（使用 \010）</span><span class="sxs-lookup"><span data-stu-id="7d65a-314">backspace (NOT SUPPORTED) (use \010)</span></span> |
| <span data-ttu-id="7d65a-315">\cK</span><span class="sxs-lookup"><span data-stu-id="7d65a-315">\cK</span></span> | <span data-ttu-id="7d65a-316">匹配控制字符 ^K （不支持）（使用 \001 等）</span><span class="sxs-lookup"><span data-stu-id="7d65a-316">control char ^K (NOT SUPPORTED) (use \001 etc)</span></span> |
| <span data-ttu-id="7d65a-317">\e</span><span class="sxs-lookup"><span data-stu-id="7d65a-317">\e</span></span> | <span data-ttu-id="7d65a-318">匹配转义符 （不支持）（使用 \033）</span><span class="sxs-lookup"><span data-stu-id="7d65a-318">escape (NOT SUPPORTED) (use \033)</span></span> |
| <span data-ttu-id="7d65a-319">\g1</span><span class="sxs-lookup"><span data-stu-id="7d65a-319">\g1</span></span> | <span data-ttu-id="7d65a-320">匹配反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-320">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-321">\g{1}</span><span class="sxs-lookup"><span data-stu-id="7d65a-321">\g{1}</span></span> | <span data-ttu-id="7d65a-322">匹配反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-322">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-323">\g{+1}</span><span class="sxs-lookup"><span data-stu-id="7d65a-323">\g{+1}</span></span> | <span data-ttu-id="7d65a-324">匹配反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-324">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-325">\g{-1}</span><span class="sxs-lookup"><span data-stu-id="7d65a-325">\g{-1}</span></span> | <span data-ttu-id="7d65a-326">匹配反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-326">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-327">\g{name}</span><span class="sxs-lookup"><span data-stu-id="7d65a-327">\g{name}</span></span> | <span data-ttu-id="7d65a-328">匹配已命名反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-328">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-329">\g&lt;name&gt;</span><span class="sxs-lookup"><span data-stu-id="7d65a-329">\g&lt;name&gt;</span></span> | <span data-ttu-id="7d65a-330">匹配子例程调用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-330">subroutine call (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-331">\g&#39;name&#39;</span><span class="sxs-lookup"><span data-stu-id="7d65a-331">\g&#39;name&#39;</span></span> | <span data-ttu-id="7d65a-332">匹配子例程调用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-332">subroutine call (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-333">\k&lt;name&gt;</span><span class="sxs-lookup"><span data-stu-id="7d65a-333">\k&lt;name&gt;</span></span> | <span data-ttu-id="7d65a-334">匹配已命名反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-334">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-335">\k&#39;name&#39;</span><span class="sxs-lookup"><span data-stu-id="7d65a-335">\k&#39;name&#39;</span></span> | <span data-ttu-id="7d65a-336">匹配已命名反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-336">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-337">\lX</span><span class="sxs-lookup"><span data-stu-id="7d65a-337">\lX</span></span> | <span data-ttu-id="7d65a-338">匹配小写 X（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-338">lowercase X (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-339">\ux</span><span class="sxs-lookup"><span data-stu-id="7d65a-339">\ux</span></span> | <span data-ttu-id="7d65a-340">匹配大写 x（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-340">uppercase x (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-341">\L...\E</span><span class="sxs-lookup"><span data-stu-id="7d65a-341">\L...\E</span></span> | <span data-ttu-id="7d65a-342">匹配小写文本 ...（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-342">lowercase text ... (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-343">\K</span><span class="sxs-lookup"><span data-stu-id="7d65a-343">\K</span></span> | <span data-ttu-id="7d65a-344">重置 $0 开头（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-344">reset beginning of $0 (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-345">\N{name}</span><span class="sxs-lookup"><span data-stu-id="7d65a-345">\N{name}</span></span> | <span data-ttu-id="7d65a-346">匹配已命名 Unicode 字符（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-346">named Unicode character (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-347">\R</span><span class="sxs-lookup"><span data-stu-id="7d65a-347">\R</span></span> | <span data-ttu-id="7d65a-348">匹配换行符（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-348">line break (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-349">\U...\E</span><span class="sxs-lookup"><span data-stu-id="7d65a-349">\U...\E</span></span> | <span data-ttu-id="7d65a-350">匹配大写文本 ...（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-350">upper case text ... (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-351">\X</span><span class="sxs-lookup"><span data-stu-id="7d65a-351">\X</span></span> | <span data-ttu-id="7d65a-352">匹配扩展 Unicode 序列（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-352">extended Unicode sequence (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-353">\%d123</span><span class="sxs-lookup"><span data-stu-id="7d65a-353">\%d123</span></span> | <span data-ttu-id="7d65a-354">匹配十进制字符 123（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-354">decimal character 123 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-355">\%xFF</span><span class="sxs-lookup"><span data-stu-id="7d65a-355">\%xFF</span></span> | <span data-ttu-id="7d65a-356">匹配十六进制字符 FF （不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-356">hex character FF (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-357">\%o123</span><span class="sxs-lookup"><span data-stu-id="7d65a-357">\%o123</span></span> | <span data-ttu-id="7d65a-358">匹配八进制字符 123（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-358">octal character 123 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-359">\%u1234</span><span class="sxs-lookup"><span data-stu-id="7d65a-359">\%u1234</span></span> | <span data-ttu-id="7d65a-360">匹配 Unicode 字符 0x1234（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-360">Unicode character 0x1234 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-361">\%U12345678</span><span class="sxs-lookup"><span data-stu-id="7d65a-361">\%U12345678</span></span> | <span data-ttu-id="7d65a-362">匹配 Unicode 字符 0x12345678（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-362">Unicode character 0x12345678 (NOT SUPPORTED) VIM</span></span> |

|  | <span data-ttu-id="7d65a-363">字符组元素</span><span class="sxs-lookup"><span data-stu-id="7d65a-363">Character class elements</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-364">x</span><span class="sxs-lookup"><span data-stu-id="7d65a-364">x</span></span> | <span data-ttu-id="7d65a-365">单个字符</span><span class="sxs-lookup"><span data-stu-id="7d65a-365">single character</span></span> |
| <span data-ttu-id="7d65a-366">A-Z</span><span class="sxs-lookup"><span data-stu-id="7d65a-366">A-Z</span></span> | <span data-ttu-id="7d65a-367">字符范围（含）</span><span class="sxs-lookup"><span data-stu-id="7d65a-367">character range (inclusive)</span></span> |
| <span data-ttu-id="7d65a-368">\d</span><span class="sxs-lookup"><span data-stu-id="7d65a-368">\d</span></span> | <span data-ttu-id="7d65a-369">匹配 Perl 字符组</span><span class="sxs-lookup"><span data-stu-id="7d65a-369">Perl character class</span></span> |
| <span data-ttu-id="7d65a-370">[:foo:]</span><span class="sxs-lookup"><span data-stu-id="7d65a-370">[:foo:]</span></span> | <span data-ttu-id="7d65a-371">匹配 ASCII 字符组 foo</span><span class="sxs-lookup"><span data-stu-id="7d65a-371">ASCII character class foo</span></span> |
| <span data-ttu-id="7d65a-372">\p{Foo}</span><span class="sxs-lookup"><span data-stu-id="7d65a-372">\p{Foo}</span></span> | <span data-ttu-id="7d65a-373">匹配 Unicode 字符组 Foo</span><span class="sxs-lookup"><span data-stu-id="7d65a-373">Unicode character class Foo</span></span> |
| <span data-ttu-id="7d65a-374">\pF</span><span class="sxs-lookup"><span data-stu-id="7d65a-374">\pF</span></span> | <span data-ttu-id="7d65a-375">匹配 Unicode 字符组 F（单字母名称）</span><span class="sxs-lookup"><span data-stu-id="7d65a-375">Unicode character class F (one-letter name)</span></span> |

|  | <span data-ttu-id="7d65a-376">作为字符组元素命名的字符组</span><span class="sxs-lookup"><span data-stu-id="7d65a-376">Named character classes as character class elements</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-377">[\d]</span><span class="sxs-lookup"><span data-stu-id="7d65a-377">[\d]</span></span> | <span data-ttu-id="7d65a-378">匹配数字字符（等价于 \d）</span><span class="sxs-lookup"><span data-stu-id="7d65a-378">digits (≡ \d)</span></span> |
| <span data-ttu-id="7d65a-379">[^\d]</span><span class="sxs-lookup"><span data-stu-id="7d65a-379">[^\d]</span></span> | <span data-ttu-id="7d65a-380">匹配非数字字符（等价于 \D）</span><span class="sxs-lookup"><span data-stu-id="7d65a-380">not digits (≡ \D)</span></span> |
| <span data-ttu-id="7d65a-381">[\D]</span><span class="sxs-lookup"><span data-stu-id="7d65a-381">[\D]</span></span> | <span data-ttu-id="7d65a-382">匹配非数字字符（等价于 \D）</span><span class="sxs-lookup"><span data-stu-id="7d65a-382">not digits (≡ \D)</span></span> |
| <span data-ttu-id="7d65a-383">[^\D]</span><span class="sxs-lookup"><span data-stu-id="7d65a-383">[^\D]</span></span> | <span data-ttu-id="7d65a-384">匹配数字字符（等价于 \d）</span><span class="sxs-lookup"><span data-stu-id="7d65a-384">not not digits (≡ \d)</span></span> |
| <span data-ttu-id="7d65a-385">[[:name:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-385">[[:name:]]</span></span> | <span data-ttu-id="7d65a-386">匹配在字符组内部命名的 ASCII 组（等价于 [:name:]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-386">named ASCII class inside character class (≡ [:name:])</span></span> |
| <span data-ttu-id="7d65a-387">[^[:name:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-387">[^[:name:]]</span></span> | <span data-ttu-id="7d65a-388">匹配在排除型字符组内部命名的 ASCII 组（等价于 [:^name:]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-388">named ASCII class inside negated character class (≡ [:^name:])</span></span> |
| <span data-ttu-id="7d65a-389">[\p{Name}]</span><span class="sxs-lookup"><span data-stu-id="7d65a-389">[\p{Name}]</span></span> | <span data-ttu-id="7d65a-390">匹配在字符组内部命名的 Unicode 属性（等价于 \p{Name}）</span><span class="sxs-lookup"><span data-stu-id="7d65a-390">named Unicode property inside character class (≡ \p{Name})</span></span> |
| <span data-ttu-id="7d65a-391">[^\p{Name}]</span><span class="sxs-lookup"><span data-stu-id="7d65a-391">[^\p{Name}]</span></span> | <span data-ttu-id="7d65a-392">匹配在排除型字符组内部命名的 Unicode 属性（等价于 \P{Name}）</span><span class="sxs-lookup"><span data-stu-id="7d65a-392">named Unicode property inside negated character class (≡ \P{Name})</span></span> |

| <a name="user-content-perl"></a> | <span data-ttu-id="7d65a-393">Perl 字符组（仅限所有 ASCII 码）</span><span class="sxs-lookup"><span data-stu-id="7d65a-393">Perl character classes (all ASCII-only)</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-394">\d</span><span class="sxs-lookup"><span data-stu-id="7d65a-394">\d</span></span> | <span data-ttu-id="7d65a-395">匹配数字字符（等价于 [0-9]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-395">digits (≡ [0-9])</span></span> |
| <span data-ttu-id="7d65a-396">\D</span><span class="sxs-lookup"><span data-stu-id="7d65a-396">\D</span></span> | <span data-ttu-id="7d65a-397">匹配非数字字符（等价于 [^0-9]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-397">not digits (≡ [^0-9])</span></span> |
| <span data-ttu-id="7d65a-398">\s</span><span class="sxs-lookup"><span data-stu-id="7d65a-398">\s</span></span> | <span data-ttu-id="7d65a-399">匹配任何空白字符（等价于 [\t\n\f\r]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-399">whitespace (≡ [\t\n\f\r])</span></span> |
| <span data-ttu-id="7d65a-400">\S</span><span class="sxs-lookup"><span data-stu-id="7d65a-400">\S</span></span> | <span data-ttu-id="7d65a-401">匹配任何非空白字符（等价于 [^\t\n\f\r]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-401">not whitespace (≡ [^\t\n\f\r])</span></span> |
| <span data-ttu-id="7d65a-402">\w</span><span class="sxs-lookup"><span data-stu-id="7d65a-402">\w</span></span> | <span data-ttu-id="7d65a-403">匹配包括下划线的任何单词字符（等价于 [0-9A-Za-z\_]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-403">word characters (≡ [0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="7d65a-404">\W</span><span class="sxs-lookup"><span data-stu-id="7d65a-404">\W</span></span> | <span data-ttu-id="7d65a-405">匹配任何非单词字符（等价于 [^0-9A-Za-z\_]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-405">not word characters (≡ [^0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="7d65a-406">\h</span><span class="sxs-lookup"><span data-stu-id="7d65a-406">\h</span></span> | <span data-ttu-id="7d65a-407">匹配水平空格（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-407">horizontal space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-408">\H</span><span class="sxs-lookup"><span data-stu-id="7d65a-408">\H</span></span> | <span data-ttu-id="7d65a-409">匹配非水平空格（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-409">not horizontal space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-410">\v</span><span class="sxs-lookup"><span data-stu-id="7d65a-410">\v</span></span> | <span data-ttu-id="7d65a-411">匹配垂直空格（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-411">vertical space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-412">\V</span><span class="sxs-lookup"><span data-stu-id="7d65a-412">\V</span></span> | <span data-ttu-id="7d65a-413">匹配非垂直空格（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-413">not vertical space (NOT SUPPORTED)</span></span> |

|<a name="user-content-ascii"></a>  | <span data-ttu-id="7d65a-414">ASCII 字符组</span><span class="sxs-lookup"><span data-stu-id="7d65a-414">ASCII character classes</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-415">[[:alnum:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-415">[[:alnum:]]</span></span> | <span data-ttu-id="7d65a-416">匹配数字与字母字符（等价于 [0-9A-Za-z]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-416">alphanumeric (≡ [0-9A-Za-z])</span></span> |
| <span data-ttu-id="7d65a-417">[[:alpha:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-417">[[:alpha:]]</span></span> | <span data-ttu-id="7d65a-418">匹配字母字符（等价于 [A-Za-z]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-418">alphabetic (≡ [A-Za-z])</span></span> |
| <span data-ttu-id="7d65a-419">[[:ascii:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-419">[[:ascii:]]</span></span> | <span data-ttu-id="7d65a-420">匹配 ASCII 字符（等价于 [\x00-\x7F]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-420">ASCII (≡ [\x00-\x7F])</span></span> |
| <span data-ttu-id="7d65a-421">[[:blank:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-421">[[:blank:]]</span></span> | <span data-ttu-id="7d65a-422">匹配制表符 （等价于[\t]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-422">blank (≡ [\t])</span></span> |
| <span data-ttu-id="7d65a-423">[[:cntrl:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-423">[[:cntrl:]]</span></span> | <span data-ttu-id="7d65a-424">匹配控制字符（等价于 [\x00-\x1F\x7F]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-424">control (≡ [\x00-\x1F\x7F])</span></span> |
| <span data-ttu-id="7d65a-425">[[:digit:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-425">[[:digit:]]</span></span> | <span data-ttu-id="7d65a-426">匹配数字字符（等价于 [0-9]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-426">digits (≡ [0-9])</span></span> |
| <span data-ttu-id="7d65a-427">[[:graph:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-427">[[:graph:]]</span></span> | <span data-ttu-id="7d65a-428">可打印与可见字符（等价于`[!-~]` 等价于 `[A-Za-z0-9!&quot;#$%&amp;&#39;()\*+,\-./:;&lt;=&gt;?@[\\\]^_`\` `{\|}~]`）</span><span class="sxs-lookup"><span data-stu-id="7d65a-428">graphical (≡ `[!-~]` ≡ `[A-Za-z0-9!&quot;#$%&amp;&#39;()\*+,\-./:;&lt;=&gt;?@[\\\]^_`\` `{\|}~]`)</span></span> |
| <span data-ttu-id="7d65a-429">[[:lower:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-429">[[:lower:]]</span></span> | <span data-ttu-id="7d65a-430">匹配小写字符（等价于 [a-z]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-430">lower case (≡ [a-z])</span></span> |
| <span data-ttu-id="7d65a-431">[[:print:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-431">[[:print:]]</span></span> | <span data-ttu-id="7d65a-432">匹配可打印字符（等价于 [-~] 等价于 [[:graph:]]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-432">printable (≡ [-~] ≡ [[:graph:]])</span></span> |
| <span data-ttu-id="7d65a-433">[[:punct:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-433">[[:punct:]]</span></span> | <span data-ttu-id="7d65a-434">匹配标点字符（等价于 [!-/:-@[-\`{-~]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-434">punctuation (≡ [!-/:-@[-\`{-~])</span></span> |
| <span data-ttu-id="7d65a-435">[[:space:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-435">[[:space:]]</span></span> | <span data-ttu-id="7d65a-436">匹配任何空白字符（等价于 [\t\n\v\f\r]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-436">whitespace (≡ [\t\n\v\f\r])</span></span> |
| <span data-ttu-id="7d65a-437">[[:upper:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-437">[[:upper:]]</span></span> | <span data-ttu-id="7d65a-438">匹配大写字符（等价于 [A-Z] ）</span><span class="sxs-lookup"><span data-stu-id="7d65a-438">upper case (≡ [A-Z])</span></span> |
| <span data-ttu-id="7d65a-439">[[:word:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-439">[[:word:]]</span></span> | <span data-ttu-id="7d65a-440">匹配包括下划线的任何单词字符（等价于 [0-9A-Za-z\_]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-440">word characters (≡ [0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="7d65a-441">[[:xdigit:]]</span><span class="sxs-lookup"><span data-stu-id="7d65a-441">[[:xdigit:]]</span></span> | <span data-ttu-id="7d65a-442">匹配十六进制数字字符（等价于 [0-9A-Fa-f]）</span><span class="sxs-lookup"><span data-stu-id="7d65a-442">hex digit (≡ [0-9A-Fa-f])</span></span> |

| | <span data-ttu-id="7d65a-443">Unicode 字符组名称 - 常规类别</span><span class="sxs-lookup"><span data-stu-id="7d65a-443">Unicode character class names--general category</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-444">C</span><span class="sxs-lookup"><span data-stu-id="7d65a-444">C</span></span> | <span data-ttu-id="7d65a-445">其他</span><span class="sxs-lookup"><span data-stu-id="7d65a-445">other</span></span> |
| <span data-ttu-id="7d65a-446">抄送</span><span class="sxs-lookup"><span data-stu-id="7d65a-446">Cc</span></span> | <span data-ttu-id="7d65a-447">control</span><span class="sxs-lookup"><span data-stu-id="7d65a-447">control</span></span> |
| <span data-ttu-id="7d65a-448">Cf</span><span class="sxs-lookup"><span data-stu-id="7d65a-448">Cf</span></span> | <span data-ttu-id="7d65a-449">format</span><span class="sxs-lookup"><span data-stu-id="7d65a-449">format</span></span> |
| <span data-ttu-id="7d65a-450">Cn</span><span class="sxs-lookup"><span data-stu-id="7d65a-450">Cn</span></span> | <span data-ttu-id="7d65a-451">未赋值（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-451">unassigned code points (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-452">Co</span><span class="sxs-lookup"><span data-stu-id="7d65a-452">Co</span></span> | <span data-ttu-id="7d65a-453">私用</span><span class="sxs-lookup"><span data-stu-id="7d65a-453">private use</span></span> |
| <span data-ttu-id="7d65a-454">Cs</span><span class="sxs-lookup"><span data-stu-id="7d65a-454">Cs</span></span> | <span data-ttu-id="7d65a-455">代理项</span><span class="sxs-lookup"><span data-stu-id="7d65a-455">surrogate</span></span> |
| <span data-ttu-id="7d65a-456">L</span><span class="sxs-lookup"><span data-stu-id="7d65a-456">L</span></span> | <span data-ttu-id="7d65a-457">字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-457">letter</span></span> |
| <span data-ttu-id="7d65a-458">LC</span><span class="sxs-lookup"><span data-stu-id="7d65a-458">LC</span></span> | <span data-ttu-id="7d65a-459">大小写字母（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-459">cased letter (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-460">L&amp;</span><span class="sxs-lookup"><span data-stu-id="7d65a-460">L&amp;</span></span> | <span data-ttu-id="7d65a-461">大小写字母（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-461">cased letter (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-462">Ll</span><span class="sxs-lookup"><span data-stu-id="7d65a-462">Ll</span></span> | <span data-ttu-id="7d65a-463">小写字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-463">lowercase letter</span></span> |
| <span data-ttu-id="7d65a-464">Lm</span><span class="sxs-lookup"><span data-stu-id="7d65a-464">Lm</span></span> | <span data-ttu-id="7d65a-465">修饰字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-465">modifier letter</span></span> |
| <span data-ttu-id="7d65a-466">Lo</span><span class="sxs-lookup"><span data-stu-id="7d65a-466">Lo</span></span> | <span data-ttu-id="7d65a-467">其他字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-467">other letter</span></span> |
| <span data-ttu-id="7d65a-468">Lt</span><span class="sxs-lookup"><span data-stu-id="7d65a-468">Lt</span></span> | <span data-ttu-id="7d65a-469">首字母大写</span><span class="sxs-lookup"><span data-stu-id="7d65a-469">titlecase letter</span></span> |
| <span data-ttu-id="7d65a-470">Lu</span><span class="sxs-lookup"><span data-stu-id="7d65a-470">Lu</span></span> | <span data-ttu-id="7d65a-471">大写字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-471">uppercase letter</span></span> |
| <span data-ttu-id="7d65a-472">M</span><span class="sxs-lookup"><span data-stu-id="7d65a-472">M</span></span> | <span data-ttu-id="7d65a-473">标记</span><span class="sxs-lookup"><span data-stu-id="7d65a-473">mark</span></span> |
| <span data-ttu-id="7d65a-474">Mc</span><span class="sxs-lookup"><span data-stu-id="7d65a-474">Mc</span></span> | <span data-ttu-id="7d65a-475">间距标记</span><span class="sxs-lookup"><span data-stu-id="7d65a-475">spacing mark</span></span> |
| <span data-ttu-id="7d65a-476">Me</span><span class="sxs-lookup"><span data-stu-id="7d65a-476">Me</span></span> | <span data-ttu-id="7d65a-477">封闭标记</span><span class="sxs-lookup"><span data-stu-id="7d65a-477">enclosing mark</span></span> |
| <span data-ttu-id="7d65a-478">Mn</span><span class="sxs-lookup"><span data-stu-id="7d65a-478">Mn</span></span> | <span data-ttu-id="7d65a-479">非间距标记</span><span class="sxs-lookup"><span data-stu-id="7d65a-479">non-spacing mark</span></span> |
| <span data-ttu-id="7d65a-480">N</span><span class="sxs-lookup"><span data-stu-id="7d65a-480">N</span></span> | <span data-ttu-id="7d65a-481">数字</span><span class="sxs-lookup"><span data-stu-id="7d65a-481">number</span></span> |
| <span data-ttu-id="7d65a-482">Nd</span><span class="sxs-lookup"><span data-stu-id="7d65a-482">Nd</span></span> | <span data-ttu-id="7d65a-483">十进制数字</span><span class="sxs-lookup"><span data-stu-id="7d65a-483">decimal number</span></span> |
| <span data-ttu-id="7d65a-484">Nl</span><span class="sxs-lookup"><span data-stu-id="7d65a-484">Nl</span></span> | <span data-ttu-id="7d65a-485">字母或数字</span><span class="sxs-lookup"><span data-stu-id="7d65a-485">letter number</span></span> |
| <span data-ttu-id="7d65a-486">否</span><span class="sxs-lookup"><span data-stu-id="7d65a-486">No</span></span> | <span data-ttu-id="7d65a-487">其他数字</span><span class="sxs-lookup"><span data-stu-id="7d65a-487">other number</span></span> |
| <span data-ttu-id="7d65a-488">P</span><span class="sxs-lookup"><span data-stu-id="7d65a-488">P</span></span> | <span data-ttu-id="7d65a-489">标点符号</span><span class="sxs-lookup"><span data-stu-id="7d65a-489">punctuation</span></span> |
| <span data-ttu-id="7d65a-490">Pc</span><span class="sxs-lookup"><span data-stu-id="7d65a-490">Pc</span></span> | <span data-ttu-id="7d65a-491">连接符</span><span class="sxs-lookup"><span data-stu-id="7d65a-491">connector punctuation</span></span> |
| <span data-ttu-id="7d65a-492">Pd</span><span class="sxs-lookup"><span data-stu-id="7d65a-492">Pd</span></span> | <span data-ttu-id="7d65a-493">短划线</span><span class="sxs-lookup"><span data-stu-id="7d65a-493">dash punctuation</span></span> |
| <span data-ttu-id="7d65a-494">Pe</span><span class="sxs-lookup"><span data-stu-id="7d65a-494">Pe</span></span> | <span data-ttu-id="7d65a-495">结束标点</span><span class="sxs-lookup"><span data-stu-id="7d65a-495">close punctuation</span></span> |
| <span data-ttu-id="7d65a-496">Pf</span><span class="sxs-lookup"><span data-stu-id="7d65a-496">Pf</span></span> | <span data-ttu-id="7d65a-497">后引号</span><span class="sxs-lookup"><span data-stu-id="7d65a-497">final punctuation</span></span> |
| <span data-ttu-id="7d65a-498">Pi</span><span class="sxs-lookup"><span data-stu-id="7d65a-498">Pi</span></span> | <span data-ttu-id="7d65a-499">前引号</span><span class="sxs-lookup"><span data-stu-id="7d65a-499">initial punctuation</span></span> |
| <span data-ttu-id="7d65a-500">Po</span><span class="sxs-lookup"><span data-stu-id="7d65a-500">Po</span></span> | <span data-ttu-id="7d65a-501">其他标点符号</span><span class="sxs-lookup"><span data-stu-id="7d65a-501">other punctuation</span></span> |
| <span data-ttu-id="7d65a-502">Ps</span><span class="sxs-lookup"><span data-stu-id="7d65a-502">Ps</span></span> | <span data-ttu-id="7d65a-503">开始标点</span><span class="sxs-lookup"><span data-stu-id="7d65a-503">open punctuation</span></span> |
| <span data-ttu-id="7d65a-504">S</span><span class="sxs-lookup"><span data-stu-id="7d65a-504">S</span></span> | <span data-ttu-id="7d65a-505">symbol</span><span class="sxs-lookup"><span data-stu-id="7d65a-505">symbol</span></span> |
| <span data-ttu-id="7d65a-506">Sc</span><span class="sxs-lookup"><span data-stu-id="7d65a-506">Sc</span></span> | <span data-ttu-id="7d65a-507">货币符号</span><span class="sxs-lookup"><span data-stu-id="7d65a-507">currency symbol</span></span> |
| <span data-ttu-id="7d65a-508">Sk</span><span class="sxs-lookup"><span data-stu-id="7d65a-508">Sk</span></span> | <span data-ttu-id="7d65a-509">修饰符符号</span><span class="sxs-lookup"><span data-stu-id="7d65a-509">modifier symbol</span></span> |
| <span data-ttu-id="7d65a-510">Sm</span><span class="sxs-lookup"><span data-stu-id="7d65a-510">Sm</span></span> | <span data-ttu-id="7d65a-511">数学符号</span><span class="sxs-lookup"><span data-stu-id="7d65a-511">math symbol</span></span> |
| <span data-ttu-id="7d65a-512">So</span><span class="sxs-lookup"><span data-stu-id="7d65a-512">So</span></span> | <span data-ttu-id="7d65a-513">其他符号</span><span class="sxs-lookup"><span data-stu-id="7d65a-513">other symbol</span></span> |
| <span data-ttu-id="7d65a-514">Z</span><span class="sxs-lookup"><span data-stu-id="7d65a-514">Z</span></span> | <span data-ttu-id="7d65a-515">分隔符</span><span class="sxs-lookup"><span data-stu-id="7d65a-515">separator</span></span> |
| <span data-ttu-id="7d65a-516">Zl</span><span class="sxs-lookup"><span data-stu-id="7d65a-516">Zl</span></span> | <span data-ttu-id="7d65a-517">行分隔符</span><span class="sxs-lookup"><span data-stu-id="7d65a-517">line separator</span></span> |
| <span data-ttu-id="7d65a-518">Zp</span><span class="sxs-lookup"><span data-stu-id="7d65a-518">Zp</span></span> | <span data-ttu-id="7d65a-519">段落分隔符</span><span class="sxs-lookup"><span data-stu-id="7d65a-519">paragraph separator</span></span> |
| <span data-ttu-id="7d65a-520">Zs</span><span class="sxs-lookup"><span data-stu-id="7d65a-520">Zs</span></span> | <span data-ttu-id="7d65a-521">空白分隔符</span><span class="sxs-lookup"><span data-stu-id="7d65a-521">space separator</span></span> |

| <span data-ttu-id="7d65a-522">Unicode 字符组名称 - 文字系统</span><span class="sxs-lookup"><span data-stu-id="7d65a-522">Unicode character class names--scripts</span></span> |
| --- |
| <span data-ttu-id="7d65a-523">阿德拉姆</span><span class="sxs-lookup"><span data-stu-id="7d65a-523">Adlam</span></span> |
| <span data-ttu-id="7d65a-524">阿霍姆语</span><span class="sxs-lookup"><span data-stu-id="7d65a-524">Ahom</span></span> |
| <span data-ttu-id="7d65a-525">安纳托利亚 \_ 象形文字</span><span class="sxs-lookup"><span data-stu-id="7d65a-525">Anatolian\_Hieroglyphs</span></span> |
| <span data-ttu-id="7d65a-526">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="7d65a-526">Arabic</span></span> |
| <span data-ttu-id="7d65a-527">亚美尼亚语</span><span class="sxs-lookup"><span data-stu-id="7d65a-527">Armenian</span></span> |
| <span data-ttu-id="7d65a-528">阿维斯陀语</span><span class="sxs-lookup"><span data-stu-id="7d65a-528">Avestan</span></span> |
| <span data-ttu-id="7d65a-529">巴厘文</span><span class="sxs-lookup"><span data-stu-id="7d65a-529">Balinese</span></span> |
| <span data-ttu-id="7d65a-530">巴姆穆文</span><span class="sxs-lookup"><span data-stu-id="7d65a-530">Bamum</span></span> |
| <span data-ttu-id="7d65a-531">Bassa\_Vah</span><span class="sxs-lookup"><span data-stu-id="7d65a-531">Bassa\_Vah</span></span> |
| <span data-ttu-id="7d65a-532">巴塔克文</span><span class="sxs-lookup"><span data-stu-id="7d65a-532">Batak</span></span> |
| <span data-ttu-id="7d65a-533">孟加拉语</span><span class="sxs-lookup"><span data-stu-id="7d65a-533">Bengali</span></span> |
| <span data-ttu-id="7d65a-534">拜克舒克文</span><span class="sxs-lookup"><span data-stu-id="7d65a-534">Bhaiksuki</span></span> |
| <span data-ttu-id="7d65a-535">汉语拼音字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-535">Bopomofo</span></span> |
| <span data-ttu-id="7d65a-536">婆罗米文</span><span class="sxs-lookup"><span data-stu-id="7d65a-536">Brahmi</span></span> |
| <span data-ttu-id="7d65a-537">布莱叶盲文</span><span class="sxs-lookup"><span data-stu-id="7d65a-537">Braille</span></span> |
| <span data-ttu-id="7d65a-538">布吉文</span><span class="sxs-lookup"><span data-stu-id="7d65a-538">Buginese</span></span> |
| <span data-ttu-id="7d65a-539">布锡语</span><span class="sxs-lookup"><span data-stu-id="7d65a-539">Buhid</span></span> |
| <span data-ttu-id="7d65a-540">加拿大 \_ 澳大利亚土著语</span><span class="sxs-lookup"><span data-stu-id="7d65a-540">Canadian\_Aboriginal</span></span> |
| <span data-ttu-id="7d65a-541">卡里亚文</span><span class="sxs-lookup"><span data-stu-id="7d65a-541">Carian</span></span> |
| <span data-ttu-id="7d65a-542">高加索 \_ 阿尔巴尼亚语</span><span class="sxs-lookup"><span data-stu-id="7d65a-542">Caucasian\_Albanian</span></span> |
| <span data-ttu-id="7d65a-543">占文</span><span class="sxs-lookup"><span data-stu-id="7d65a-543">Chakma</span></span> |
| <span data-ttu-id="7d65a-544">Cham</span><span class="sxs-lookup"><span data-stu-id="7d65a-544">Cham</span></span> |
| <span data-ttu-id="7d65a-545">切罗基语</span><span class="sxs-lookup"><span data-stu-id="7d65a-545">Cherokee</span></span> |
| <span data-ttu-id="7d65a-546">花剌子模语</span><span class="sxs-lookup"><span data-stu-id="7d65a-546">Chorasmian</span></span> |
| <span data-ttu-id="7d65a-547">通用</span><span class="sxs-lookup"><span data-stu-id="7d65a-547">Common</span></span> |
| <span data-ttu-id="7d65a-548">科普特语</span><span class="sxs-lookup"><span data-stu-id="7d65a-548">Coptic</span></span> |
| <span data-ttu-id="7d65a-549">楔形文字</span><span class="sxs-lookup"><span data-stu-id="7d65a-549">Cuneiform</span></span> |
| <span data-ttu-id="7d65a-550">塞浦路斯语</span><span class="sxs-lookup"><span data-stu-id="7d65a-550">Cypriot</span></span> |
| <span data-ttu-id="7d65a-551">西里尔字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-551">Cyrillic</span></span> |
| <span data-ttu-id="7d65a-552">德塞莱特文</span><span class="sxs-lookup"><span data-stu-id="7d65a-552">Deseret</span></span> |
| <span data-ttu-id="7d65a-553">梵文</span><span class="sxs-lookup"><span data-stu-id="7d65a-553">Devanagari</span></span> |
| <span data-ttu-id="7d65a-554">Dives \_ Akuru</span><span class="sxs-lookup"><span data-stu-id="7d65a-554">Dives\_Akuru</span></span> |
| <span data-ttu-id="7d65a-555">多格兰语</span><span class="sxs-lookup"><span data-stu-id="7d65a-555">Dogra</span></span> |
| <span data-ttu-id="7d65a-556">杜普洛伊速记体</span><span class="sxs-lookup"><span data-stu-id="7d65a-556">Duployan</span></span> |
| <span data-ttu-id="7d65a-557">埃及 \_ 象形文字</span><span class="sxs-lookup"><span data-stu-id="7d65a-557">Egyptian\_Hieroglyphs</span></span> |
| <span data-ttu-id="7d65a-558">爱尔巴桑语</span><span class="sxs-lookup"><span data-stu-id="7d65a-558">Elbasan</span></span> |
| <span data-ttu-id="7d65a-559">埃利迈语</span><span class="sxs-lookup"><span data-stu-id="7d65a-559">Elymaic</span></span> |
| <span data-ttu-id="7d65a-560">埃塞俄比亚文</span><span class="sxs-lookup"><span data-stu-id="7d65a-560">Ethiopic</span></span> |
| <span data-ttu-id="7d65a-561">格鲁吉亚语</span><span class="sxs-lookup"><span data-stu-id="7d65a-561">Georgian</span></span> |
| <span data-ttu-id="7d65a-562">格拉哥里语</span><span class="sxs-lookup"><span data-stu-id="7d65a-562">Glagolitic</span></span> |
| <span data-ttu-id="7d65a-563">哥特语</span><span class="sxs-lookup"><span data-stu-id="7d65a-563">Gothic</span></span> |
| <span data-ttu-id="7d65a-564">格兰塔字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-564">Grantha</span></span> |
| <span data-ttu-id="7d65a-565">希腊语</span><span class="sxs-lookup"><span data-stu-id="7d65a-565">Greek</span></span> |
| <span data-ttu-id="7d65a-566">古吉拉特语</span><span class="sxs-lookup"><span data-stu-id="7d65a-566">Gujarati</span></span> |
| <span data-ttu-id="7d65a-567">Gunjala \_Gondi</span><span class="sxs-lookup"><span data-stu-id="7d65a-567">Gunjala\_Gondi</span></span> |
| <span data-ttu-id="7d65a-568">锡克教文</span><span class="sxs-lookup"><span data-stu-id="7d65a-568">Gurmukhi</span></span> |
| <span data-ttu-id="7d65a-569">汉语</span><span class="sxs-lookup"><span data-stu-id="7d65a-569">Han</span></span> |
| <span data-ttu-id="7d65a-570">韩语</span><span class="sxs-lookup"><span data-stu-id="7d65a-570">Hangul</span></span> |
| <span data-ttu-id="7d65a-571">Hanifi \ _Rohingya</span><span class="sxs-lookup"><span data-stu-id="7d65a-571">Hanifi\_Rohingya</span></span> |
| <span data-ttu-id="7d65a-572">汉奴劳族文</span><span class="sxs-lookup"><span data-stu-id="7d65a-572">Hanunoo</span></span> |
| <span data-ttu-id="7d65a-573">哈特兰文</span><span class="sxs-lookup"><span data-stu-id="7d65a-573">Hatran</span></span> |
| <span data-ttu-id="7d65a-574">希伯来语</span><span class="sxs-lookup"><span data-stu-id="7d65a-574">Hebrew</span></span> |
| <span data-ttu-id="7d65a-575">日文</span><span class="sxs-lookup"><span data-stu-id="7d65a-575">Hiragana</span></span> |
| <span data-ttu-id="7d65a-576">英制文字 \_ 阿拉姆语</span><span class="sxs-lookup"><span data-stu-id="7d65a-576">Imperial\_Aramaic</span></span> |
| <span data-ttu-id="7d65a-577">继承</span><span class="sxs-lookup"><span data-stu-id="7d65a-577">Inherited</span></span> |
| <span data-ttu-id="7d65a-578">碑文 \_ 巴拉维语</span><span class="sxs-lookup"><span data-stu-id="7d65a-578">Inscriptional\_Pahlavi</span></span> |
| <span data-ttu-id="7d65a-579">碑文 \_ 帕提亚语</span><span class="sxs-lookup"><span data-stu-id="7d65a-579">Inscriptional\_Parthian</span></span> |
| <span data-ttu-id="7d65a-580">爪哇文</span><span class="sxs-lookup"><span data-stu-id="7d65a-580">Javanese</span></span> |
| <span data-ttu-id="7d65a-581">凯提文</span><span class="sxs-lookup"><span data-stu-id="7d65a-581">Kaithi</span></span> |
| <span data-ttu-id="7d65a-582">埃纳德语</span><span class="sxs-lookup"><span data-stu-id="7d65a-582">Kannada</span></span> |
| <span data-ttu-id="7d65a-583">片假名</span><span class="sxs-lookup"><span data-stu-id="7d65a-583">Katakana</span></span> |
| <span data-ttu-id="7d65a-584">克耶 \_ 列支敦士登</span><span class="sxs-lookup"><span data-stu-id="7d65a-584">Kayah\_Li</span></span> |
| <span data-ttu-id="7d65a-585">卡罗须提文</span><span class="sxs-lookup"><span data-stu-id="7d65a-585">Kharoshthi</span></span> |
| <span data-ttu-id="7d65a-586">契丹 \_小\_文字</span><span class="sxs-lookup"><span data-stu-id="7d65a-586">Khitan\_Small\_Script</span></span> |
| <span data-ttu-id="7d65a-587">高棉语</span><span class="sxs-lookup"><span data-stu-id="7d65a-587">Khmer</span></span> |
| <span data-ttu-id="7d65a-588">克吉奇文</span><span class="sxs-lookup"><span data-stu-id="7d65a-588">Khojki</span></span> |
| <span data-ttu-id="7d65a-589">信德文</span><span class="sxs-lookup"><span data-stu-id="7d65a-589">Khudawadi</span></span> |
| <span data-ttu-id="7d65a-590">老挝语</span><span class="sxs-lookup"><span data-stu-id="7d65a-590">Lao</span></span> |
| <span data-ttu-id="7d65a-591">拉丁语</span><span class="sxs-lookup"><span data-stu-id="7d65a-591">Latin</span></span> |
| <span data-ttu-id="7d65a-592">雷布查文</span><span class="sxs-lookup"><span data-stu-id="7d65a-592">Lepcha</span></span> |
| <span data-ttu-id="7d65a-593">林布文</span><span class="sxs-lookup"><span data-stu-id="7d65a-593">Limbu</span></span> |
| <span data-ttu-id="7d65a-594">线性 \_A</span><span class="sxs-lookup"><span data-stu-id="7d65a-594">Linear\_A</span></span> |
| <span data-ttu-id="7d65a-595">线性 \_B</span><span class="sxs-lookup"><span data-stu-id="7d65a-595">Linear\_B</span></span> |
| <span data-ttu-id="7d65a-596">僳文傈</span><span class="sxs-lookup"><span data-stu-id="7d65a-596">Lisu</span></span> |
| <span data-ttu-id="7d65a-597">利西亚文</span><span class="sxs-lookup"><span data-stu-id="7d65a-597">Lycian</span></span> |
| <span data-ttu-id="7d65a-598">吕底亚文</span><span class="sxs-lookup"><span data-stu-id="7d65a-598">Lydian</span></span> |
| <span data-ttu-id="7d65a-599">马哈詹语</span><span class="sxs-lookup"><span data-stu-id="7d65a-599">Mahajani</span></span> |
| <span data-ttu-id="7d65a-600">望加锡语</span><span class="sxs-lookup"><span data-stu-id="7d65a-600">Makasar</span></span> |
| <span data-ttu-id="7d65a-601">马拉雅拉姆语</span><span class="sxs-lookup"><span data-stu-id="7d65a-601">Malayalam</span></span> |
| <span data-ttu-id="7d65a-602">阿拉米文</span><span class="sxs-lookup"><span data-stu-id="7d65a-602">Mandaic</span></span> |
| <span data-ttu-id="7d65a-603">摩尼文</span><span class="sxs-lookup"><span data-stu-id="7d65a-603">Manichaean</span></span> |
| <span data-ttu-id="7d65a-604">Marchen</span><span class="sxs-lookup"><span data-stu-id="7d65a-604">Marchen</span></span> |
| <span data-ttu-id="7d65a-605">Masaram\_Gondi</span><span class="sxs-lookup"><span data-stu-id="7d65a-605">Masaram\_Gondi</span></span> |
| <span data-ttu-id="7d65a-606">梅德法伊德林文</span><span class="sxs-lookup"><span data-stu-id="7d65a-606">Medefaidrin</span></span> |
| <span data-ttu-id="7d65a-607">梅泰族 \_ 曼尼普尔文</span><span class="sxs-lookup"><span data-stu-id="7d65a-607">Meetei\_Mayek</span></span> |
| <span data-ttu-id="7d65a-608">门德 \_ 门迪文</span><span class="sxs-lookup"><span data-stu-id="7d65a-608">Mende\_Kikakui</span></span> |
| <span data-ttu-id="7d65a-609">麦罗埃 \_ 手写体</span><span class="sxs-lookup"><span data-stu-id="7d65a-609">Meroitic\_Cursive</span></span> |
| <span data-ttu-id="7d65a-610">麦罗埃 \_ 象形文字</span><span class="sxs-lookup"><span data-stu-id="7d65a-610">Meroitic\_Hieroglyphs</span></span> |
| <span data-ttu-id="7d65a-611">苗文</span><span class="sxs-lookup"><span data-stu-id="7d65a-611">Miao</span></span> |
| <span data-ttu-id="7d65a-612">莫迪文</span><span class="sxs-lookup"><span data-stu-id="7d65a-612">Modi</span></span> |
| <span data-ttu-id="7d65a-613">蒙古语</span><span class="sxs-lookup"><span data-stu-id="7d65a-613">Mongolian</span></span> |
| <span data-ttu-id="7d65a-614">毛里塔尼亚乌吉亚</span><span class="sxs-lookup"><span data-stu-id="7d65a-614">Mro</span></span> |
| <span data-ttu-id="7d65a-615">穆尔塔尼</span><span class="sxs-lookup"><span data-stu-id="7d65a-615">Multani</span></span> |
| <span data-ttu-id="7d65a-616">缅甸</span><span class="sxs-lookup"><span data-stu-id="7d65a-616">Myanmar</span></span> |
| <span data-ttu-id="7d65a-617">纳巴泰</span><span class="sxs-lookup"><span data-stu-id="7d65a-617">Nabataean</span></span> |
| <span data-ttu-id="7d65a-618">楠迪梵文</span><span class="sxs-lookup"><span data-stu-id="7d65a-618">Nandinagari</span></span> |
| <span data-ttu-id="7d65a-619">New\_Tai\_Lue</span><span class="sxs-lookup"><span data-stu-id="7d65a-619">New\_Tai\_Lue</span></span> |
| <span data-ttu-id="7d65a-620">印度比哈尔邦</span><span class="sxs-lookup"><span data-stu-id="7d65a-620">Newa</span></span> |
| <span data-ttu-id="7d65a-621">Nko</span><span class="sxs-lookup"><span data-stu-id="7d65a-621">Nko</span></span> |
| <span data-ttu-id="7d65a-622">女书</span><span class="sxs-lookup"><span data-stu-id="7d65a-622">Nushu</span></span> |
| <span data-ttu-id="7d65a-623">Nyiakeng \ _Puachue \ _Hmong</span><span class="sxs-lookup"><span data-stu-id="7d65a-623">Nyiakeng\_Puachue\_Hmong</span></span> |
| <span data-ttu-id="7d65a-624">欧甘字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-624">Ogham</span></span> |
| <span data-ttu-id="7d65a-625">Ol\_Chiki</span><span class="sxs-lookup"><span data-stu-id="7d65a-625">Ol\_Chiki</span></span> |
| <span data-ttu-id="7d65a-626">古语 \_ 匈牙利语</span><span class="sxs-lookup"><span data-stu-id="7d65a-626">Old\_Hungarian</span></span> |
| <span data-ttu-id="7d65a-627">古语 \_ 意大利语</span><span class="sxs-lookup"><span data-stu-id="7d65a-627">Old\_Italic</span></span> |
| <span data-ttu-id="7d65a-628">古语 \_ 北部 \_ 阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="7d65a-628">Old\_North\_Arabian</span></span> |
| <span data-ttu-id="7d65a-629">古语 \_ 彼尔姆语</span><span class="sxs-lookup"><span data-stu-id="7d65a-629">Old\_Permic</span></span> |
| <span data-ttu-id="7d65a-630">古语 \_ 波斯语</span><span class="sxs-lookup"><span data-stu-id="7d65a-630">Old\_Persian</span></span> |
| <span data-ttu-id="7d65a-631">古语 \_ 古索格代亚纳语</span><span class="sxs-lookup"><span data-stu-id="7d65a-631">Old\_Sogdian</span></span> |
| <span data-ttu-id="7d65a-632">古语 \_ 南部 \_ 阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="7d65a-632">Old\_South\_Arabian</span></span> |
| <span data-ttu-id="7d65a-633">古语 \_ 突厥语</span><span class="sxs-lookup"><span data-stu-id="7d65a-633">Old\_Turkic</span></span> |
| <span data-ttu-id="7d65a-634">奥里雅语</span><span class="sxs-lookup"><span data-stu-id="7d65a-634">Oriya</span></span> |
| <span data-ttu-id="7d65a-635">欧塞奇语</span><span class="sxs-lookup"><span data-stu-id="7d65a-635">Osage</span></span> |
| <span data-ttu-id="7d65a-636">奥斯曼亚字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-636">Osmanya</span></span> |
| <span data-ttu-id="7d65a-637">救世苗文 \_ 苗语</span><span class="sxs-lookup"><span data-stu-id="7d65a-637">Pahawh\_Hmong</span></span> |
| <span data-ttu-id="7d65a-638">帕米拉语</span><span class="sxs-lookup"><span data-stu-id="7d65a-638">Palmyrene</span></span> |
| <span data-ttu-id="7d65a-639">Pau\_Cin\_Hau</span><span class="sxs-lookup"><span data-stu-id="7d65a-639">Pau\_Cin\_Hau</span></span> |
| <span data-ttu-id="7d65a-640">Phags\_Pa</span><span class="sxs-lookup"><span data-stu-id="7d65a-640">Phags\_Pa</span></span> |
| <span data-ttu-id="7d65a-641">腓尼基语</span><span class="sxs-lookup"><span data-stu-id="7d65a-641">Phoenician</span></span> |
| <span data-ttu-id="7d65a-642">Psalter \ _Pahlavi</span><span class="sxs-lookup"><span data-stu-id="7d65a-642">Psalter\_Pahlavi</span></span> |
| <span data-ttu-id="7d65a-643">勒姜语</span><span class="sxs-lookup"><span data-stu-id="7d65a-643">Rejang</span></span> |
| <span data-ttu-id="7d65a-644">古北欧文字</span><span class="sxs-lookup"><span data-stu-id="7d65a-644">Runic</span></span> |
| <span data-ttu-id="7d65a-645">撒马利亚文</span><span class="sxs-lookup"><span data-stu-id="7d65a-645">Samaritan</span></span> |
| <span data-ttu-id="7d65a-646">索拉什特拉文</span><span class="sxs-lookup"><span data-stu-id="7d65a-646">Saurashtra</span></span> |
| <span data-ttu-id="7d65a-647">夏拉达文</span><span class="sxs-lookup"><span data-stu-id="7d65a-647">Sharada</span></span> |
| <span data-ttu-id="7d65a-648">萧伯纳文</span><span class="sxs-lookup"><span data-stu-id="7d65a-648">Shavian</span></span> |
| <span data-ttu-id="7d65a-649">悉昙文字</span><span class="sxs-lookup"><span data-stu-id="7d65a-649">Siddham</span></span> |
| <span data-ttu-id="7d65a-650">手语书写体</span><span class="sxs-lookup"><span data-stu-id="7d65a-650">SignWriting</span></span> |
| <span data-ttu-id="7d65a-651">僧伽罗语</span><span class="sxs-lookup"><span data-stu-id="7d65a-651">Sinhala</span></span> |
| <span data-ttu-id="7d65a-652">粟特语</span><span class="sxs-lookup"><span data-stu-id="7d65a-652">Sogdian</span></span> |
| <span data-ttu-id="7d65a-653">Sora\_Sompeng</span><span class="sxs-lookup"><span data-stu-id="7d65a-653">Sora\_Sompeng</span></span> |
| <span data-ttu-id="7d65a-654">索永布语</span><span class="sxs-lookup"><span data-stu-id="7d65a-654">Soyombo</span></span> |
| <span data-ttu-id="7d65a-655">巽他语</span><span class="sxs-lookup"><span data-stu-id="7d65a-655">Sundanese</span></span> |
| <span data-ttu-id="7d65a-656">Syloti\_Nagri</span><span class="sxs-lookup"><span data-stu-id="7d65a-656">Syloti\_Nagri</span></span> |
| <span data-ttu-id="7d65a-657">叙利亚语</span><span class="sxs-lookup"><span data-stu-id="7d65a-657">Syriac</span></span> |
| <span data-ttu-id="7d65a-658">他加禄语</span><span class="sxs-lookup"><span data-stu-id="7d65a-658">Tagalog</span></span> |
| <span data-ttu-id="7d65a-659">塔班瓦语</span><span class="sxs-lookup"><span data-stu-id="7d65a-659">Tagbanwa</span></span> |
| <span data-ttu-id="7d65a-660">Tai\_Le</span><span class="sxs-lookup"><span data-stu-id="7d65a-660">Tai\_Le</span></span> |
| <span data-ttu-id="7d65a-661">Tai\_Tham</span><span class="sxs-lookup"><span data-stu-id="7d65a-661">Tai\_Tham</span></span> |
| <span data-ttu-id="7d65a-662">Tai\_Viet</span><span class="sxs-lookup"><span data-stu-id="7d65a-662">Tai\_Viet</span></span> |
| <span data-ttu-id="7d65a-663">泰克里文</span><span class="sxs-lookup"><span data-stu-id="7d65a-663">Takri</span></span> |
| <span data-ttu-id="7d65a-664">泰米尔语</span><span class="sxs-lookup"><span data-stu-id="7d65a-664">Tamil</span></span> |
| <span data-ttu-id="7d65a-665">西夏语</span><span class="sxs-lookup"><span data-stu-id="7d65a-665">Tangut</span></span> |
| <span data-ttu-id="7d65a-666">泰卢固语</span><span class="sxs-lookup"><span data-stu-id="7d65a-666">Telugu</span></span> |
| <span data-ttu-id="7d65a-667">它拿字母</span><span class="sxs-lookup"><span data-stu-id="7d65a-667">Thaana</span></span> |
| <span data-ttu-id="7d65a-668">泰语</span><span class="sxs-lookup"><span data-stu-id="7d65a-668">Thai</span></span> |
| <span data-ttu-id="7d65a-669">藏语</span><span class="sxs-lookup"><span data-stu-id="7d65a-669">Tibetan</span></span> |
| <span data-ttu-id="7d65a-670">提夫纳语</span><span class="sxs-lookup"><span data-stu-id="7d65a-670">Tifinagh</span></span> |
| <span data-ttu-id="7d65a-671">底罗仆多文</span><span class="sxs-lookup"><span data-stu-id="7d65a-671">Tirhuta</span></span> |
| <span data-ttu-id="7d65a-672">乌加里特语</span><span class="sxs-lookup"><span data-stu-id="7d65a-672">Ugaritic</span></span> |
| <span data-ttu-id="7d65a-673">瓦依语</span><span class="sxs-lookup"><span data-stu-id="7d65a-673">Vai</span></span> |
| <span data-ttu-id="7d65a-674">万秋文</span><span class="sxs-lookup"><span data-stu-id="7d65a-674">Wancho</span></span> |
| <span data-ttu-id="7d65a-675">Warang\_Citi</span><span class="sxs-lookup"><span data-stu-id="7d65a-675">Warang\_Citi</span></span> |
| <span data-ttu-id="7d65a-676">雅兹迪语</span><span class="sxs-lookup"><span data-stu-id="7d65a-676">Yezidi</span></span> |
| <span data-ttu-id="7d65a-677">彝语</span><span class="sxs-lookup"><span data-stu-id="7d65a-677">Yi</span></span> |
| <span data-ttu-id="7d65a-678">Zanabazar\_Square</span><span class="sxs-lookup"><span data-stu-id="7d65a-678">Zanabazar\_Square</span></span> |

|  | <span data-ttu-id="7d65a-679">Vim 字符组</span><span class="sxs-lookup"><span data-stu-id="7d65a-679">Vim character classes</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-680">\i</span><span class="sxs-lookup"><span data-stu-id="7d65a-680">\i</span></span> | <span data-ttu-id="7d65a-681">匹配标识符字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-681">identifier character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-682">\I</span><span class="sxs-lookup"><span data-stu-id="7d65a-682">\I</span></span> | <span data-ttu-id="7d65a-683">\i 不包括数字字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-683">\i except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-684">\k</span><span class="sxs-lookup"><span data-stu-id="7d65a-684">\k</span></span> | <span data-ttu-id="7d65a-685">匹配关键字字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-685">keyword character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-686">\K</span><span class="sxs-lookup"><span data-stu-id="7d65a-686">\K</span></span> | <span data-ttu-id="7d65a-687">\k 不包括数字字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-687">\k except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-688">\f</span><span class="sxs-lookup"><span data-stu-id="7d65a-688">\f</span></span> | <span data-ttu-id="7d65a-689">匹配文件名称字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-689">file name character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-690">\F</span><span class="sxs-lookup"><span data-stu-id="7d65a-690">\F</span></span> | <span data-ttu-id="7d65a-691">\f 不包括数字字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-691">\f except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-692">\p</span><span class="sxs-lookup"><span data-stu-id="7d65a-692">\p</span></span> | <span data-ttu-id="7d65a-693">匹配可打印字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-693">printable character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-694">\P</span><span class="sxs-lookup"><span data-stu-id="7d65a-694">\P</span></span> | <span data-ttu-id="7d65a-695">\p 不包括数字字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-695">\p except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-696">\s</span><span class="sxs-lookup"><span data-stu-id="7d65a-696">\s</span></span> | <span data-ttu-id="7d65a-697">匹配空白字符（等价于 [\t]）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-697">whitespace character (≡ [\t]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-698">\S</span><span class="sxs-lookup"><span data-stu-id="7d65a-698">\S</span></span> | <span data-ttu-id="7d65a-699">匹配非空白字符（等价于 [\t]）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-699">non-white space character (≡ [^ \t]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-700">\d</span><span class="sxs-lookup"><span data-stu-id="7d65a-700">\d</span></span> | <span data-ttu-id="7d65a-701">匹配数字字符（等价于 [0-9]）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-701">digits (≡ [0-9]) VIM</span></span> |
| <span data-ttu-id="7d65a-702">\D</span><span class="sxs-lookup"><span data-stu-id="7d65a-702">\D</span></span> | <span data-ttu-id="7d65a-703">非 \d VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-703">not \d VIM</span></span> |
| <span data-ttu-id="7d65a-704">\x</span><span class="sxs-lookup"><span data-stu-id="7d65a-704">\x</span></span> | <span data-ttu-id="7d65a-705">匹配十六进制数字字符（等价于 [0-9A-Fa-f]）（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-705">hex digits (≡ [0-9A-Fa-f]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-706">\X</span><span class="sxs-lookup"><span data-stu-id="7d65a-706">\X</span></span> | <span data-ttu-id="7d65a-707">非 \x（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-707">not \x (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-708">\o</span><span class="sxs-lookup"><span data-stu-id="7d65a-708">\o</span></span> | <span data-ttu-id="7d65a-709">匹配八进制数字字符（等价于 [0-7]）（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-709">octal digits (≡ [0-7]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-710">\O</span><span class="sxs-lookup"><span data-stu-id="7d65a-710">\O</span></span> | <span data-ttu-id="7d65a-711">非 \o（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-711">not \o (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-712">\w</span><span class="sxs-lookup"><span data-stu-id="7d65a-712">\w</span></span> | <span data-ttu-id="7d65a-713">匹配单词字符 VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-713">word character VIM</span></span> |
| <span data-ttu-id="7d65a-714">\W</span><span class="sxs-lookup"><span data-stu-id="7d65a-714">\W</span></span> | <span data-ttu-id="7d65a-715">非 \w VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-715">not \w VIM</span></span> |
| <span data-ttu-id="7d65a-716">\h</span><span class="sxs-lookup"><span data-stu-id="7d65a-716">\h</span></span> | <span data-ttu-id="7d65a-717">匹配单词起始字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-717">head of word character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-718">\H</span><span class="sxs-lookup"><span data-stu-id="7d65a-718">\H</span></span> | <span data-ttu-id="7d65a-719">非 \h（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-719">not \h (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-720">\a</span><span class="sxs-lookup"><span data-stu-id="7d65a-720">\a</span></span> | <span data-ttu-id="7d65a-721">匹配字母字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-721">alphabetic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-722">\A</span><span class="sxs-lookup"><span data-stu-id="7d65a-722">\A</span></span> | <span data-ttu-id="7d65a-723">非 \a（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-723">not \a (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-724">\l</span><span class="sxs-lookup"><span data-stu-id="7d65a-724">\l</span></span> | <span data-ttu-id="7d65a-725">匹配小写字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-725">lowercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-726">\L</span><span class="sxs-lookup"><span data-stu-id="7d65a-726">\L</span></span> | <span data-ttu-id="7d65a-727">匹配非小写字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-727">not lowercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-728">\u</span><span class="sxs-lookup"><span data-stu-id="7d65a-728">\u</span></span> | <span data-ttu-id="7d65a-729">匹配大写字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-729">uppercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-730">\U</span><span class="sxs-lookup"><span data-stu-id="7d65a-730">\U</span></span> | <span data-ttu-id="7d65a-731">匹配非大写（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-731">not uppercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-732">\_x</span><span class="sxs-lookup"><span data-stu-id="7d65a-732">\_x</span></span> | <span data-ttu-id="7d65a-733">\x 加上换行符，匹配任意 x（不支持） VIM </span><span class="sxs-lookup"><span data-stu-id="7d65a-733">\x plus newline, for any x (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-734">\c</span><span class="sxs-lookup"><span data-stu-id="7d65a-734">\c</span></span> | <span data-ttu-id="7d65a-735">忽略大小写（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-735">ignore case (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-736">\C</span><span class="sxs-lookup"><span data-stu-id="7d65a-736">\C</span></span> | <span data-ttu-id="7d65a-737">匹配大小写（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-737">match case (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-738">\m</span><span class="sxs-lookup"><span data-stu-id="7d65a-738">\m</span></span> | <span data-ttu-id="7d65a-739">magic（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-739">magic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-740">\M</span><span class="sxs-lookup"><span data-stu-id="7d65a-740">\M</span></span> | <span data-ttu-id="7d65a-741">nomagic（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-741">nomagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-742">\v</span><span class="sxs-lookup"><span data-stu-id="7d65a-742">\v</span></span> | <span data-ttu-id="7d65a-743">verymagic（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-743">verymagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-744">\V</span><span class="sxs-lookup"><span data-stu-id="7d65a-744">\V</span></span> | <span data-ttu-id="7d65a-745">verynomagic（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-745">verynomagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="7d65a-746">\Z</span><span class="sxs-lookup"><span data-stu-id="7d65a-746">\Z</span></span> | <span data-ttu-id="7d65a-747">忽略 Unicode 组合字符的不同（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="7d65a-747">ignore differences in Unicode combining characters (NOT SUPPORTED) VIM</span></span> |

|  | <span data-ttu-id="7d65a-748">Magic</span><span class="sxs-lookup"><span data-stu-id="7d65a-748">Magic</span></span> |
| --- | --- |
| <span data-ttu-id="7d65a-749">(?{code})</span><span class="sxs-lookup"><span data-stu-id="7d65a-749">(?{code})</span></span> | <span data-ttu-id="7d65a-750">PERL 中的任意 Perl 代码（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-750">arbitrary Perl code (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="7d65a-751">(??{code})</span><span class="sxs-lookup"><span data-stu-id="7d65a-751">(??{code})</span></span> | <span data-ttu-id="7d65a-752">PERL 中延迟的任意 Perl 代码（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-752">postponed arbitrary Perl code (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="7d65a-753">(?n)</span><span class="sxs-lookup"><span data-stu-id="7d65a-753">(?n)</span></span> | <span data-ttu-id="7d65a-754">递归调用 regexp 捕获组 n （不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-754">recursive call to regexp capturing group n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-755">(?+n)</span><span class="sxs-lookup"><span data-stu-id="7d65a-755">(?+n)</span></span> | <span data-ttu-id="7d65a-756">递归调用相对组 +n （不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-756">recursive call to relative group +n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-757">(?-n)</span><span class="sxs-lookup"><span data-stu-id="7d65a-757">(?-n)</span></span> | <span data-ttu-id="7d65a-758">递归调用相对组 -n （不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-758">recursive call to relative group -n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-759">(?C)</span><span class="sxs-lookup"><span data-stu-id="7d65a-759">(?C)</span></span> | <span data-ttu-id="7d65a-760">PCRE 回调（不支持） PCRE</span><span class="sxs-lookup"><span data-stu-id="7d65a-760">PCRE callout (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="7d65a-761">(?R)</span><span class="sxs-lookup"><span data-stu-id="7d65a-761">(?R)</span></span> | <span data-ttu-id="7d65a-762">递归调用整个 regexp （等价于 (?0)）（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-762">recursive call to entire regexp (≡ (?0)) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-763">(?&amp;name)</span><span class="sxs-lookup"><span data-stu-id="7d65a-763">(?&amp;name)</span></span> | <span data-ttu-id="7d65a-764">递归调用已命名组（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-764">recursive call to named group (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-765">(?P=name)</span><span class="sxs-lookup"><span data-stu-id="7d65a-765">(?P=name)</span></span> | <span data-ttu-id="7d65a-766">匹配已命名反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-766">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-767">(?P&gt;name)</span><span class="sxs-lookup"><span data-stu-id="7d65a-767">(?P&gt;name)</span></span> | <span data-ttu-id="7d65a-768">递归调用已命名组（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-768">recursive call to named group (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-769">(?(cond)true</span><span class="sxs-lookup"><span data-stu-id="7d65a-769">(?(cond)true</span></span>|<span data-ttu-id="7d65a-770">false)</span><span class="sxs-lookup"><span data-stu-id="7d65a-770">false)</span></span> | <span data-ttu-id="7d65a-771">条件分支（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-771">conditional branch (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-772">(?(cond)true)</span><span class="sxs-lookup"><span data-stu-id="7d65a-772">(?(cond)true)</span></span> | <span data-ttu-id="7d65a-773">条件分支（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-773">conditional branch (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-774">(\*ACCEPT)</span><span class="sxs-lookup"><span data-stu-id="7d65a-774">(\*ACCEPT)</span></span> | <span data-ttu-id="7d65a-775">让 regexps 更类似于 Prolog （不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-775">make regexps more like Prolog (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-776">(\*COMMIT)</span><span class="sxs-lookup"><span data-stu-id="7d65a-776">(\*COMMIT)</span></span> | <span data-ttu-id="7d65a-777">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-777">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-778">(\*F)</span><span class="sxs-lookup"><span data-stu-id="7d65a-778">(\*F)</span></span> | <span data-ttu-id="7d65a-779">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-779">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-780">(\*FAIL)</span><span class="sxs-lookup"><span data-stu-id="7d65a-780">(\*FAIL)</span></span> | <span data-ttu-id="7d65a-781">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-781">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-782">(\*MARK)</span><span class="sxs-lookup"><span data-stu-id="7d65a-782">(\*MARK)</span></span> | <span data-ttu-id="7d65a-783">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-783">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-784">(\*PRUNE)</span><span class="sxs-lookup"><span data-stu-id="7d65a-784">(\*PRUNE)</span></span> | <span data-ttu-id="7d65a-785">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-785">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-786">(\*SKIP)</span><span class="sxs-lookup"><span data-stu-id="7d65a-786">(\*SKIP)</span></span> | <span data-ttu-id="7d65a-787">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-787">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-788">(\*THEN)</span><span class="sxs-lookup"><span data-stu-id="7d65a-788">(\*THEN)</span></span> | <span data-ttu-id="7d65a-789">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-789">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-790">(\*ANY)</span><span class="sxs-lookup"><span data-stu-id="7d65a-790">(\*ANY)</span></span> | <span data-ttu-id="7d65a-791">设置换行约定（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-791">set newline convention (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-792">(\*ANYCRLF)</span><span class="sxs-lookup"><span data-stu-id="7d65a-792">(\*ANYCRLF)</span></span> | <span data-ttu-id="7d65a-793">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-793">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-794">(\*CR)</span><span class="sxs-lookup"><span data-stu-id="7d65a-794">(\*CR)</span></span> | <span data-ttu-id="7d65a-795">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-795">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-796">(\*CRLF)</span><span class="sxs-lookup"><span data-stu-id="7d65a-796">(\*CRLF)</span></span> | <span data-ttu-id="7d65a-797">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-797">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-798">(\*LF)</span><span class="sxs-lookup"><span data-stu-id="7d65a-798">(\*LF)</span></span> | <span data-ttu-id="7d65a-799">（不支持）</span><span class="sxs-lookup"><span data-stu-id="7d65a-799">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="7d65a-800">(\*BSR\_ANYCRLF)</span><span class="sxs-lookup"><span data-stu-id="7d65a-800">(\*BSR\_ANYCRLF)</span></span> | <span data-ttu-id="7d65a-801">设置 \R 约定（不支持） PCRE</span><span class="sxs-lookup"><span data-stu-id="7d65a-801">set \R convention (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="7d65a-802">(\*BSR\_UNICODE)</span><span class="sxs-lookup"><span data-stu-id="7d65a-802">(\*BSR\_UNICODE)</span></span> | <span data-ttu-id="7d65a-803">（不支持）PCRE</span><span class="sxs-lookup"><span data-stu-id="7d65a-803">(NOT SUPPORTED) PCRE</span></span> |

## <span data-ttu-id="7d65a-804">内容许可证</span><span class="sxs-lookup"><span data-stu-id="7d65a-804">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="7d65a-805">本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。</span><span class="sxs-lookup"><span data-stu-id="7d65a-805">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="7d65a-806">可在[此处](https://github.com/google/re2/wiki/Syntax)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="7d65a-806">The original page can be found [here](https://github.com/google/re2/wiki/Syntax).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="7d65a-807">此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。</span><span class="sxs-lookup"><span data-stu-id="7d65a-807">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="7d65a-808">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d65a-808">See also</span></span>

- [<span data-ttu-id="7d65a-809">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="7d65a-809">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)