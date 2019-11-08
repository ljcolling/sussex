#' Install a package in the Uni of Sussex home dir
#'
#' This installs packages hosted on GitHub, because the
#' University of Sussex computer labs have trouble
#' installing packages from GitHub.
#'
#' @param package.name A name of a pacakge
#' @param install.dir The installation direction (default: University of Sussex User R library)
#' @param home.dir The home director (default: University of Sussex user home director)
#'
#' @examples
#' install.sussex(package.name = "paaspkg")
#'
#' @export
install.sussex <- function(package.name, install.dir = "N:/Documents/R/win-library/3.6", home.dir = "N:/Documents/"){

  payload = utils::read.csv(url("https://raw.githubusercontent.com/ljcolling/textfiles/master/package_payloads.csv"))

  remotefile = payload[payload$name == package.name,]$url

  tempfile = file.path(home.dir,"temp.zip")

  utils::download.file(url = as.character(remotefile), dest = tempfile)



  utils::unzip(zipfile = tempfile, exdir = install.dir)

  base::file.remove(tempfile)

}

#' List packages
#'
#' This gives a list of packages that can be installed
#'
#' @examples
#' list.sussex()
#'
#' @export
list.sussex <- function(){
  payload = utils::read.csv(url("https://raw.githubusercontent.com/ljcolling/textfiles/master/package_payloads.csv"))
  as.character(payload$name)
}

