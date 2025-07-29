---
title: stata-dta
description: High-performance DuckDB extension for reading Stata .dta files
date: 2025-07-29
language: cpp
authors:
- koren
categories:
- duckdb
- cpp
code: |-
    -- Load the extension
    LOAD stata_dta;
    
    -- Read Stata file directly into DuckDB
    SELECT * FROM read_stata_dta('data/survey.dta');
    
    -- Query with SQL operations
    SELECT region, AVG(income) 
    FROM read_stata_dta('data/survey.dta') 
    GROUP BY region;
download_url: "https://github.com/codedthinking/stata-dta"
tags:
- data
- stata
- duckdb
---

A high-performance DuckDB extension that enables direct reading of Stata `.dta` data files into DuckDB tables without intermediate conversion. Supports Stata file versions 105-119 with efficient streaming processing, automatic format detection, and full SQL integration.

Key features:
- Native SQL access to Stata datasets
- Support for multiple data types and missing values
- Memory-efficient chunked reading for large files
- Thread-safe stateless design
- Cross-platform compatibility with big/little-endian support