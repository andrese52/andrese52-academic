+++
title = "Installing and configuring BLAST in Linux"
date = 2017-03-03
tags= ['blast', 'linux' , 'configuration']
math = false
highlight = true
summary= "Whenever I'm setting up new virtual machines to work on them, it is usually a problem when I try to run blast and I have to point out where the database is located. This post shows how to set up a configuration file for blast so you don't have to type the full path to the database"
+++


# Installing BLAST

Blast is a tool utilized by most molecular biologists and bioinformaticians to query one or multiple sequences with any NCBI database hosted online. Very often, the non-redundant database (nt) is utilized for these queries. However, there are others.
