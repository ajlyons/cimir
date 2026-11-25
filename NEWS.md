# cimir 0.4.2 (2026-11-23)

Updates in this version were made in a fork of cimir by [@ajlyons](https://github.com/ajlyons/cimir), as it is unclear if mkoohafkan is still maintaining the package.

Merged pull request #6 (https://github.com/mkoohafkan/cimir/pull/6) by @cbuelo containing changes required to make CIMIR work with the overhaul of the [CIMIS API](https://cimis.water.ca.gov/web-api/rest-api/latest) in June 2026.

Removed 'CIMIS ETo' from both the daily and hourly variables in `dataitems.xlsx`, because these have been 
removed in the [new CIMIS API](https://cimis.water.ca.gov/web-api/rest-api/latest). 
(Use `day-asce-eto` or `hly-asce-eto` instead). Updated the dataitems and dataflags internal data objects.

Added `readxl` and `usethis` to Suggests (because they're required to regenerate the data files)

Fixed broken ROxygen links in the documentation 

`basic_query()`: Improved code that traps and reports API errors.

`cimis_data()`: Changed the `prioritizeSCS` URL parameter in the legacy API to [`prefer`](https://cimis.water.ca.gov/web-api/rest-api/latest). No change to the function arguments.

# cimir 0.4-1 (2021-02-17)

This patch provides better handling of queries
that return empty record sets.

# cimir 0.4-0 (2020-01-22)

This release includes the following changes:

- References to defunct functions were removed.
- Minor changes to internals to meet new requirements in latest versions 
  of `tidyr` and `rlang` packages.
- Fixed bug in function `cimis_to_datetime()` regarding timezone 
  specification.
- Fixed bug in function `cimis_split_query()` where sub-queries 
  sometimes exceeded the specified length.
- New function `cimis_flags()` provides information on CIMIS Quality 
  Control flags.
- Added a new vignette describing helper functions.
- Error is returned if an empty or NULL API key is passed to 
  `set_key()`.
- Informative error message is returned when the CIMIS API itself 
  rejects a request.


# cimir 0.3-0 (2019-06-10)

This release includes the following changes:

- **(Breaking change)** Deprecated functions are now defunct.
- Package import "Rcurl" replaced with "curl" (>= 3.3).
- Data items not listed in the CIMIS Web API documentation were 
  identified and added to output of `cimis_items()`.
- Function `cimis_to_datetime()` now explicitly uses Etc/GMT+8 
  timezone to ensure match with standard timezone used by CIMIS (PST).
- New helper function `cimis_split_query()` splits a long-duration 
  query into multiple smaller-duration queries.
- New helper function `cimis_compass_to_degrees()` returns the middle 
  azimuths of a vector of compass direction labels.
- New helper function `cimis_format_location()` formats station 
  latitudes and longitudes as either decimal degrees (numeric) or 
  Hours Minutes Seconds.
- Text encoding of Web API results are set to "UTF-8", fixing potential 
  formatting issues.
- HTTP errors now include the message text provided by CIMIS to 
  describe the issue.

# cimir 0.2-0 (2019-03-14)

This release includes the following changes:

- **(Warning)** Function names have been updated to follow best 
  (or at least better) practices for avoiding
  naming conflicts and improving clarity. Old function names
  have been deprecated.
- HTTPS is now used to access the CIMIS web API.
- The URL formatting has bee updated to reflect a change in
  how the CIMIS web API formats the prioritizeSCS argument.
- The quickstart vignette has been updated to use the new function
  names.

# cimir 0.1-0 (2019-01-04)

This is the first submission of this package to CRAN. 
