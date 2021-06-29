# ProgrammingAssignment2..
## I just simply set the input y as a matrix
## and then set the solved value "z" as a null
## then with it i decided to changed every reference from "mean" to "solve"
makeCacheMatrix <- function(x = matrix(sample(1:100,9),3,3)) {
  z <- NULL
  set <- function(y) {
    y <<- y
    z <<- NULL
  }
  get <- function() y
  setsolve <- function(solve) z <<- solve
  getsolve <- function() z
  list(set = set, get = get,
       setsolve = setsolve,
       getsolve = getsolve)
}
##
## Same here, changed from "mean" to "solve" and "a" to "b"
cacheSolve <- function(x, ...) {
  b <- x$getsolve()
  if(!is.null(b)) {
    message("getting inversed matrix")
    return(b)
  }
  data <- x$get()
  s <- solve(data, ...)
  x$setsolve(b)
  b
}
